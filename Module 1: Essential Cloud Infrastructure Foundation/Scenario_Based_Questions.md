## Scenario 01 – VM to VM Communication (Low Latency)

### Situation
- Two Compute Engine VMs
- Same VPC
- Different zones
- Same region (us-central1)
- Requirement: lowest latency & lowest cost

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

