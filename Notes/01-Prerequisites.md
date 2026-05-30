# Prerequisites:
## How the web works:

**Browser:** Acts as a gateway; fetches and displays web content (Chrome, Firefox, Safari)
**URL Parsing:** Breaks address into: protocol (https://), domain (pizzayum.com), path (/menu), query (?id=123)
**DNS Lookup:** Translates domain name → IP address (e.g. 192.0.2.1) so browser can locate the server
**HTTP request:** Browser sends a request to the server; HTTPS is the encrypted, secure version (uses SSL/TLS)
**Server response:** Server receives → processes → fetches content → sends HTML back to browser
**TCP/IP:** TCP/IPUnderlying protocol that ensures data is correctly sent and reassembled over the internet
**TLS/SSL:** Encrypts data in transit when using HTTPS; protects against interception

## Web server vs HTTP server

**Web server —** the hardware + software combo that stores and delivers website files
**HTTP server (Apache / Nginx) —** software layer that processes HTTP/HTTPS requests and manages browser–server communication

## Databases

- **Store dynamic content:** menus, orders, user profiles, reviews
- **SQLRelational databases (MySQL, PostgreSQL) —** structured, query-based
- **NoSQLNon-relational (MongoDB) —** flexible, unstructured; used in large/complex apps
- Server queries DB and returns data (HTML + JSON) to the browser for rendering

## Web security essentials

**Authentication —** proving identity (login with username/password)
**Authorization —** what an authenticated user is allowed to access
***Cookies & sessions —*** remember login state and cart items across requests
**XSS** Attackers inject malicious scripts to steal data
**CSRF** Tricks users into making unwanted requests (e.g. changing account settings)
**Defences:** input validation, HTTP headers, Content Security Policy (CSP)

## Web development — front-end, back-end, full-stack

**Front-end-** Everything the user sees — HTML (structure), CSS (styling), JavaScript (interactivity)
**Back-endBehind-**-the-scenes logic — server, database, programming languages (PHP, Python, Ruby, Java)
**Full-stack-**Combines both; can build complete web applications independently

## Developer tools & ecosystem

**Text editors** — VS Code (feature-rich), Sublime Text (lightweight)
**Version control** — Git tracks code changes; GitHub stores and shares repos
**Frameworks & libraries** — React (UI), Bootstrap (responsive CSS), Node.js (back-end JS runtime)
**Browsers** — also used for testing and debugging via built-in developer tools

# Core Web Development Terminologies

## What is an API?
- API (Application Programming Interface) = a middleman between two software systems
- Allows apps to talk to each other and exchange data in a structured way
- Connects frontend and backend invisibly

### Why APIs matter for full stack developers
- **Fetch live data** — use JavaScript to call APIs and pull real-time data (user profiles, product listings, order status)
- **Build backend APIs** — handle business logic, interact with databases, send responses to frontend
- **Integrate external services** — payments (Stripe), maps (Google Maps), auth (Auth0, Firebase)

### Real-world flow (food delivery app)
1. Browse restaurants → app sends location to server via API → server returns nearby results
2. Place order → API sends order details to restaurant's system
3. Track status → API updates "Preparing" / "Out for Delivery" in real time
4. Live tracking → Google Maps API fetches and displays delivery partner's live location

---

## What is JSON?
- JSON (JavaScript Object Notation) = standard format for web data exchange
- Lightweight and human-readable
- Used whenever a frontend and backend communicate through an API

### JSON structure
```json
{
  "name": "Sara",
  "email": "sara@example.com",
  "isPremiumUser": true
}
```
- Data is stored as **key-value pairs**
- Text values go inside `" "`
- Booleans and numbers don't need quotes
- Supports arrays and nested objects

### How JSON is used in full stack projects
- **Receive data from APIs** — user profiles, product lists, orders
- **Send data to backend** — forms, login info, checkout details
- **Store data in frontend** — session info, cart data, UI settings (local storage / state)

---

## HTML vs XML

| Feature | XML | HTML |
|---|---|---|
| Full name | Extensible Markup Language | HyperText Markup Language |
| Purpose | Store and transport data | Display data in a browser |
| Tags | User-defined (e.g. `<book>`, `<price>`) | Predefined (e.g. `<h1>`, `<div>`) |
| Case sensitivity | Case-sensitive (`<Name>` ≠ `<name>`) | Not case-sensitive |
| Syntax strictness | Strict — every tag must be closed | Flexible — missing tags often tolerated |
| Visual output | No visual display | Designed for visual presentation |

### Quick summary
- **HTML** → for browsers (display)
- **XML** → for system-to-system communication (data transport)
- **JSON** → most common modern choice for web app data exchange

# Web Hosting, DNS & CMS — Notes

---

## Web Hosting

### What is web hosting?
- Stores your website's files (HTML, CSS, images) on servers so it's accessible 24/7
- When someone types your domain, the server sends files to their browser
- Servers typically run **Linux** for stability and reliability

### Website hosting setup — step by step
1. **Domain registration** — buy a unique domain name (e.g. www.yoursite.com)
2. **Choose a hosting provider** — based on storage, bandwidth, security, and support
3. **Server configuration** — provider allocates space (shared, VPS, dedicated, or cloud)
4. **Upload website files** — transfer HTML, CSS, images via FTP or cPanel
5. **Database setup** — configure MySQL / PostgreSQL for dynamic content (e.g. WordPress)
6. **DNS configuration** — point domain name to the server's IP address
7. **Website goes live** — after DNS propagates globally, your site becomes accessible
8. **Ongoing maintenance** — regular updates, security checks, backups, performance checks
9. **Handle traffic** — scale bandwidth/storage or upgrade plan as traffic grows
10. **Technical support** — troubleshoot downtime, slow performance, or errors

### Key factors when choosing a hosting provider
- Cost, server uptime, customer support, scalability, security features

### Useful tools
| Purpose | Tool |
|---|---|
| Domain availability | GoDaddy |
| DNS propagation status | WhatsMyDNS |
| DNS lookup (public records) | MXToolbox |
| Global uptime check | GeoPeeker |
| Uptime monitoring | UptimeRobot |
| Page speed test | GTmetrix / Pingdom |
| DNS + WHOIS checker | DNSChecker / ICANN WHOIS |
| IP & geolocation info | IPinfo |

---

## DNS (Domain Name System)

### What is DNS?
- Translates human-readable domain names into IP addresses
- Without DNS, you'd have to memorise numeric IPs for every website

### How DNS works — step by step
1. User types domain (e.g. `www.geeksforgeeks.org`) into browser
2. **Local cache check** — browser checks if it already has the IP stored
3. **DNS resolver** — if not cached, query goes to a resolver (usually from ISP)
4. **Root DNS server** — resolver asks root server, which identifies the TLD (.org)
5. **TLD server** — directs resolver to the authoritative DNS server for that domain
6. **Authoritative DNS server** — holds the actual IP address, sends it back to resolver
7. **Final response** — browser connects to the server and loads the page

> The entire process happens in milliseconds.

### Types of DNS queries
- **Recursive** — resolver must return either the answer or an error
- **Iterative** — resolver returns the best available answer at each step
- **Non-recursive** — answer is already in cache, no external query needed

### DNS caching & TTL
- DNS records are cached locally to avoid repeated external queries
- **TTL (Time-to-Live)** — how long a record stays cached before expiring
- Example: TTL = 3600 seconds → record cached for 1 hour, then fresh lookup required

### Types of DNS records
| Record | Purpose | Example |
|---|---|---|
| **A** | Maps domain → IPv4 address | `example.com → 192.0.2.1` |
| **AAAA** | Maps domain → IPv6 address | `example.com → 2001:0db8...` |
| **MX** | Directs email to mail servers | `example.com → mail.example.com` |
| **CNAME** | Aliases one domain to another | `www.example.com → example.com` |
| **TXT** | Stores text data (SPF, DKIM, domain verification) | SPF record string |
| **NS** | Defines authoritative name servers | `ns1.hostingprovider.com` |
| **SRV** | Location for specific services (VoIP, chat) | Port + protocol + target |
| **PTR** | Reverse lookup — IP → domain | Used for email server verification |

### Types of domains
- **Generic TLDs** — .com, .org, .net, .edu
- **Country code TLDs** — .in (India), .us, .uk, .jp
- **Inverse domains** — used for reverse DNS lookups (IP → domain name)

---

## CMS (Content Management System)

### What is a CMS?
- Lets teams create, edit, manage, and publish website content **without coding**
- Used for websites, blogs, landing pages, e-commerce stores

### Why companies use a CMS
- Easy updates — non-developers can change text, images, links
- Saves time and cost — no need to build from scratch every time
- Multi-user collaboration — marketing, design, editors can all work together
- Built-in SEO tools and plugin support

---

## WordPress

- Most widely used CMS — powers **43%+ of websites globally**
- Launched in 2003 as a blogging platform; now used for all website types
- Built on **PHP**

### Popular WordPress plugins
| Plugin | Purpose |
|---|---|
| **Yoast SEO** | Improve Google ranking and SEO performance |
| **WooCommerce** | Turns site into a fully functional online store |
| **Elementor** | Drag-and-drop page builder, no coding needed |
| **WP Rocket** | Performance optimisation — caching, faster load times |

> **Note:** WordPress is becoming outdated for modern apps — PHP can be slow and hard to scale. Many companies are now shifting to JavaScript/TypeScript-based CMS platforms.

---

## Payload CMS

- Modern CMS built on **JavaScript / TypeScript (Node.js)**
- Integrates natively with **Next.js** for fast, scalable, dynamic websites
- Gives developers full control over the frontend
- Good choice when **data ownership and privacy** are priorities (self-hosted, no third-party SaaS)

### Popular Payload plugins
| Plugin | Purpose |
|---|---|
| **payload-visual-editor** | Visual editor in admin UI for non-coders |
| **payload-ai** | AI-assisted content creation and management |
| **payload-auth-plugin** | OAuth and OpenID Connect authentication |
| **payload-plugin-author-fields** | Auto-adds `createdBy` / `updatedBy` tracking fields |

### Companies using Payload over WordPress
| Company | Use case |
|---|---|
| **Microsoft** | Dynamic campaign hub |
| **Blue Origin** | Student postcard campaign |
| **Sonos** | Campaign hub with high UX standards |
| **ASICS** | Global ambassador platform |
| **Hello Bello** | Scalable e-commerce store |

---

## WordPress vs Payload — quick comparison

| | WordPress | Payload CMS |
|---|---|---|
| Language | PHP | JavaScript / TypeScript |
| Best for | Blogs, simple business sites | Modern, scalable web apps |
| Ease of use | Very beginner-friendly | Developer-focused |
| Flexibility | Plugin-dependent | Highly customisable |
| Scalability | Limited at scale | Built for scale |
| Data ownership | Depends on hosting | Self-hosted, full control |