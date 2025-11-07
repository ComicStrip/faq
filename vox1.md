⸻

🧠 Umbrel Local Access Issue (HTTP vs HTTPS)

Lady Vox’s screenshots show she’s running Umbrel locally (umbrel.local).
Her problem is almost certainly related to HTTP vs HTTPS.

⸻

🔍 The Problem
	•	Umbrel’s local dashboard (umbrel.local) only uses HTTP by default — it’s not a public website, it’s a local server inside your network.
	•	Modern browsers (especially Chrome and Edge) may force HTTPS connections to .local domains.
	•	When that happens, the browser tries https://umbrel.local, which fails because Umbrel doesn’t serve HTTPS locally.

✅ In short: The computer is refusing to connect via HTTP, which is exactly what’s blocking Umbrel.

⸻

✅ The Fixes

Option 1: Force HTTP manually

Type this exactly in your browser’s address bar:

http://umbrel.local

Make sure there is no “s” in http.
If it automatically changes to https://, proceed to Option 2.

⸻

Option 2: Clear HSTS cache (Chrome / Edge)

If your browser keeps forcing HTTPS for umbrel.local, clear its HTTPS rules:
	1.	Open this page in Chrome or Edge:

chrome://net-internals/#hsts


	2.	Scroll down to Delete domain security policies.
	3.	Enter:

umbrel.local


	4.	Click Delete.
	5.	Try visiting:

http://umbrel.local



⸻

Option 3: Access Umbrel via local IP address

If .local still doesn’t work:
	1.	Find Umbrel’s local IP address on your network:
	•	Look it up in your router’s device list, or
	•	Use a network scanner app like Fing on your phone.
	2.	Once you have the IP, open it directly, e.g.:

http://192.168.1.42

(Replace 192.168.1.42 with your actual Umbrel IP.)

⸻

Option 4: Use Tor Browser (optional)

If you’ve enabled Tor access in Umbrel settings, you can connect securely using your .onion address in Tor Browser.
This bypasses local HTTPS issues entirely.

⸻

⚙️ Summary

Problem	Browser forces HTTPS → Umbrel only serves HTTP locally
Fix 1	Use http://umbrel.local
Fix 2	Clear HSTS cache in Chrome/Edge
Fix 3	Use Umbrel’s local IP (e.g. http://192.168.1.42)
Fix 4	Use Tor Browser with your .onion address


⸻

Would you like me to include a short guide (for Windows or macOS) on how to find Umbrel’s IP address easily?
