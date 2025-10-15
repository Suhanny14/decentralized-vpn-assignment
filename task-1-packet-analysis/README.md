# Task 1: Network Traffic Analysis 📡

**Points:** 20

### Part A: Browser DevTools Analysis- NO INSTALLATION NEEDED!

**Tools:** Chrome/Firefox DevTools (Built-in)

#### What to do:

1. Open your browser's DevTools (F12 or Right-click → Inspect)
2. Go to the **Network** tab
3. Visit these 3 websites:
   - `http://neverssl.com`
   - `https://github.com`
   - `https://youtube.com`
   -

#### Answer these in `browser-analysis.md`:

**1. HTTP vs HTTPS Comparison**

- Take a screenshot of the Network tab for each website
- Compare the request headers between HTTP and HTTPS
- Can you see the actual data in HTTP requests? What about HTTPS?
- Why is one more secure than the other?

**2. Request Analysis**

- How many total requests were made for each website?
- What types of resources were loaded? (HTML, CSS, JS, Images, etc.)
- Which website made the most requests and why?
- **3. Performance Insights**
- What was the total load time for each website?
- Which requests took the longest?
- Find one request and explain these timing phases:
  - DNS Lookup
  - Connection Time
  - Waiting (TTFB)

---

### Part B: Wireshark Packet Analysis

**Tools:** Wireshark

#### What to do:

1. Install Wireshark from [wireshark.org](https://www.wireshark.org/download.html)
2. Start a capture on your active network interface
3. Visit the same 3 websites from Part A
4. Capture for **5 minutes**
5.

#### Answer these in `wireshark-analysis.md`:

**1. Protocol Distribution**

- Go to Statistics → Protocol Hierarchy
- Screenshot the protocol hierarchy
- List the top 5 protocols and their percentages
- Explain what each protocol does (in your own words)

**2. DNS Query Analysis**

- Apply filter: `dns`
- Find 3 DNS queries in your capture
- For each query, document:
  - Domain being queried
  - DNS server IP
  - Response IP address
  - Response time
- Screenshot showing DNS query and response packets

**3. TCP Three-Way Handshake**

- Apply filter: `tcp.flags.syn==1`
- Find ONE complete handshake (SYN → SYN-ACK → ACK)
- Screenshot all 3 packets
- Explain in your own words:
  - What is SYN?
  - What is SYN-ACK?
  - What is ACK?
  - Why do we need this handshake?

**4. HTTP vs HTTPS in Packets)**

- Apply filter: `http`
- Can you read the actual HTTP request/response?
- Now try filter: `tls` or `ssl` (for HTTPS traffic)
- Can you read the encrypted data?
- Screenshot both and explain the difference
- Why can't you see HTTPS content even though you captured it?

---

## Deliverables

Create a folder: `submissions/your-name-task1/` containing:

```
your-name-task1/
├── browser-analysis.md       # Your browser DevTools analysis
├── wireshark-analysis.md     # Your Wireshark packet analysis
└── screenshots/
    ├── browser-http.png
    ├── browser-https.png
    ├── protocol-hierarchy.png
    ├── dns-queries.png
    ├── tcp-handshake.png
    ├── http-plaintext.png
    └── https-encrypted.png
```

---

## What We're Looking For

- Explain concepts in your own words
- Show you understand WHY things work, not just WHAT they are
- Well-labeled screenshots
- Compare and contrast (HTTP vs HTTPS, Browser view vs Packet view)
- Draw insights from your observations
