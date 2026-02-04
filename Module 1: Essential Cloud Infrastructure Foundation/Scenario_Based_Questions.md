## Scenario 01 – VM to VM Communication (Low Latency)

### Situation
- Two Compute Engine VMs
- Same VPC
- Different zones
- Same region (us-central1)
- Requirement: lowest latency & lowest cost

### Options
> 1. Assign a static external IP to vm-db and have vm-web connect to it using that IP.
> 2. Use the default internal DNS name to connect from vm-web to vm-db.
> 3. Create a Global Load Balancer to route traffic between the two instances.
> 4. Configure a VPN tunnel between the two zones to encrypt the traffic.

### Best Solution ✅
**Use internal IP / internal DNS for communication**

### Why This Is Correct
- GCP VPC is global
- Traffic stays on Google private network
- No internet egress cost
- No extra configuration

### Why Other Options Are Wrong ❌
- External IP → higher latency & cost
- Load Balancer → unnecessary overhead
- VPN → meant for different networks

### Exam Shortcut 🧠
> Same VPC → Internal DNS / Internal IP

