## **Assignment: “Across the Internet” — Understanding and Building the Network**

---

## **Part A – Follow the Packet (Research + Explanation Task)**

**Scenario:**
You’re sitting in India and send a message to a friend whose PC is in Germany. Describe how that single message actually travels from your machine to theirs.

Your explanation should clearly trace the path of the packet through all the layers and systems that touch it.

### **Guidelines**

Break down the story logically:

1. **Application Layer:** What actually happens when you hit “send”? (e.g., HTTP/TCP sockets, DNS query, etc.)
2. **Transport Layer:** How does TCP or UDP handle it? What handshake or segmentation occurs?
3. **Network Layer:** How is the IP packet addressed and routed across continents? (mention routers, BGP, NAT, etc.)
4. **Data Link & Physical Layers:** How does it travel through local networks, fiber optics, ISPs?
5. **Reverse Path:** How the response finds its way back.

Also include:

- The role of DNS resolution.
- The difference between routing inside your ISP vs across autonomous systems.
- The effect of congestion or packet loss.
- A simple **diagram** showing the packet’s approximate route (you can draw it or use tools like traceroute + any free diagram maker).
- Optional: mention how HTTPS modifies or secures the exchange.

**Deliverable:**
A short written report (800–1200 words max) with a clear diagram.
You’re being judged on depth of understanding, not on the length of the submission.

---

## **Part B – Hands-On: “Build Your Own Mini DHCP & DNS Simulator”**

### **Task**

Build a Python program that simulates a **tiny local network** with:

- A **DHCP server** that assigns IPs dynamically to clients.
- A **DNS server** that resolves names (like `example.local`) to IPs inside the simulated network.
- At least **two clients** (can just be simulated objects) that:

  - Request IPs via DHCP.
  - Use DNS to look up another client and “ping” it (even if it’s a mock ping).

You don’t need actual sockets or multiple PCs — a single script simulating the message flow is fine.
Bonus if you use **real socket code** and can show packets being exchanged locally.

**Expected flow:**

1. Client A boots → sends DHCP DISCOVER → server assigns IP.
2. Client A asks DNS server for `clientB.local` → gets IP.
3. Client A “pings” Client B (mock or actual socket send).

### **Deliverables**

- Python code with clear logs showing the interactions.
- A short explanation (300–500 words) of how each protocol fits into the overall communication flow.

**Bonus ideas:**

- Show IP leases expiring or being re-assigned.
- Add a simple web interface to visualize clients joining/leaving.
- Use `scapy` for real packet crafting.

---

## **Submission**

- One GitHub repo containing:

  - `/PartA_Report.pdf`
  - `/PartB_Code/` folder
  - `/README.md` explaining how to run and what they learned

---

## **Evaluation Criteria**

| Area                                 | Weight |
| ------------------------------------ | ------ |
| Conceptual clarity (Part A)          | 40 %   |
| Functionality & correctness (Part B) | 35 %   |
| Code structure and readability       | 15 %   |
| Creativity / depth of thought        | 10 %   |
