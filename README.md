# DNS Resolution: Iterative and Recursive Lookup

This project implements both **iterative** and **recursive** DNS lookups using the [dnspython](https://www.dnspython.org/) library. It demonstrates how to:
- Start an **iterative** DNS resolution from the root nameservers down to the authoritative nameserver.
- Use the **recursive** approach via a system or default DNS resolver.

---

## 1. How to Clone and Set Up

### 1.1 Cloning the Repository
1. Open a terminal and run:
   ```bash
   git clone https://github.com/kn-joshua/CS425-A2.git
   ```

2. Navigate to the cloned directory:
   ```bash
   cd CS425-A2
   ```

### 1.2 Installing Dependencies
This project depends on the **dnspython** library for DNS queries. To install it, run:

```bash
pip install dnspython
```

*(Make sure your Python environment or virtual environment is correctly set up.)*

## 2. Running the Code
Inside the cloned directory, you will find `dnsresolver.py`. You can run **two modes** of DNS resolution: **iterative** or **recursive**.

### 2.1 General Usage
```bash
python3 dnsresolver.py <mode> <domain>
```
* `<mode>`: Must be either `iterative` or `recursive`.
* `<domain>`: The domain name you want to resolve (e.g., `google.com`).

### 2.2 Examples
* **Iterative Resolution**:
  ```bash
  python3 dnsresolver.py iterative google.com
  ```
  This starts from the root DNS servers and iteratively queries TLD and authoritative nameservers until it retrieves the final IP address (or fails).

* **Recursive Resolution**:
  ```bash
  python3 dnsresolver.py recursive google.com
  ```
  This relies on your system's default resolver (such as Google DNS or your ISP's DNS) to handle the full resolution process.

## 3. Testing & Error Cases
We tested this script with valid domains and also simulated various **error scenarios**. Depending on the DNS query results, you may see:

* `NXDOMAIN` (Non-Existent Domain):
  ```text
  [ERROR] Domain <domain> does not exist.
  ```

* `NoAnswer` (No valid answer was received):
  ```text
  [ERROR] No answer for the query.
  ```

* `Timeout`:
  ```text
  [ERROR] Query timed out.
  ```

* Other unforeseen errors:
  ```text
  [ERROR] Recursive lookup failed: <error_message>
  ```

## 4. Declaration
I/We declare that the code and documentation provided here are our own work, and any external resources used have been properly credited. No part of this submission involves unauthorized copying or plagiarism.
