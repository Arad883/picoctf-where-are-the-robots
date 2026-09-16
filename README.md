# picoctf-where-are-the-robots

## Challenge Info

- **Challenge Name:** Where Are the Robots
- **Platform:** picoCTF
- **Category:** Web
- **Difficulty:** Easy
- **Status:** Retired / Practice
---

## Summary

In this challenge, we are given a simple website and need to find the "robots."  
The term "robots" refers to the standard `robots.txt` file, which tells search engine crawlers which paths not to index.

The key point is that `robots.txt` is not designed to hide information.  
If a developer puts a sensitive path in it, they are actually revealing that path to everyone.

---

## Prerequisites

- Basic familiarity with HTTP and URLs
- Basic knowledge of browser Developer Tools
- Understanding of what `robots.txt` is
- Simple curiosity :)

---

## Solution Steps

### 1. Open the challenge website

First, open the challenge URL in your browser.  
The page usually shows a simple message or a basic website.

### 2. Check `robots.txt`

Navigate to:

```text
/robots.txt
```

For example:

```text
https://<challenge-url>/robots.txt
```

You will typically see something like:

```text
User-agent: *
Disallow: /1bb4.html
```

This means the developer did not want search engines to index the path /1bb4.html.
But that same line reveals the hidden path to us.

### 3. Go to the disclosed path

Now navigate to:

```text
/1bb4.html
```

For example:

```text
https://<challenge-url>/1bb4.html
```

The flag is displayed on this page:

```text
picoCTF{[redacted]}
```

---

## Key Insight

robots.txt is a tool for managing search engine crawling, not a security mechanism.
Any path listed under Disallow effectively announces to everyone that the path exists.

This is a common mistake in web development:
A developer thinks robots.txt hides information, but it actually exposes it further.

---

## Lessons Learned

· Always check robots.txt first when testing a web target.
· robots.txt can reveal hidden paths, admin panels, backup files, and more.
· Do not overlook HTML source code and auxiliary files like sitemap.xml.
· Real security should never rely on obscurity.

---

## Disclaimer

This writeup is provided for educational and defensive purposes only.
No complete solver, malicious code, or real flag is published in this repository.
Please respect CTF platform rules and privacy.

---
