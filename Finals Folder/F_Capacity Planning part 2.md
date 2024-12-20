![image](https://github.com/user-attachments/assets/619aac0a-b5e8-4d7a-b368-d3841cb55b11)


**Part 2. Network Scalability Analysis**

Recall the e-commerce website scenario we discussed earlier. Given the
expected surge in traffic, analyze the provided network topology
diagram. Identify potential bottlenecks and areas where scalability
might be a concern. Propose specific strategies to improve the
network\'s scalability and performance to ensure a seamless user
experience during the peak traffic period. Consider factors such as
increased user demand, new applications, and security threats.

![image](https://github.com/user-attachments/assets/96d22e12-194b-4190-aea4-ec90ee71f760)

Proposed Network Topology Design For Scalability

![Balanza_Sabado_NetworkTopologyDesignForScalability](https://github.com/user-attachments/assets/562b6082-88f6-403d-bc55-7060212a0095)


**Network Analysis**

In the old network design case, Layer 2 switches directly connect to
VLAN1, VLAN2, and VLAN3. All these switches are connected to the
multilayer switch\'s central device. The multilayer switch centralizes
the entire network before it is connected to the edge router that leads
to the internet. The good thing about VLANS is that they provide logical
separation in traffic for managing and reducing broadcast domains.
However, the size of the multilayer switch must be such that it does not
become a choke point for all these VLANs. The same applies when
considering uplinks from layer 2 switches towards core devices; enough
bandwidth should be available so that no congestions occur at any time.
Looking at the security of the network, it has no firewalls or other
security measures included into it. Therefore, if there is no proper
policy implemented or ACL in place then the network can easily get
jeopardized by external anomalies or internally among each other.
Another issue that may pose a growing hindrance to the scalability of
this network occurs if Layer 2 switches run out of ports or if an edge
switch cannot handle an increased traffic load due to expansion in size
for example through the acquisition of additional sites by the
organization. Additionally, the servers are standalone with no backup
allowing the possibility of downtime, especially during peak hours.

**Scalability Planning**

This design supports both vertical and horizontal scaling making it
highly scalable, which means adding additional servers and devices
requires no significant structural changes. In addition, managing
increasing user loads would become easier because VLANs on the network
help separate traffic logically. Additionally, the availability of
backup servers for every server on the network offers redundancy. Core
and access layer switches are also offered as additional port capacity
in case of expansion. Generally, this topology will make sure that the
network is growing along with the demand for the website at peak hours,
and even after, it balances the traffic through multiple paths with high
performance.

**Evaluation of Solutions**

The network design specified has thorough scalability approaches.
Multilayer switches ensure efficient traffic management and inter-VLAN
process routing, and firewalls protect systems from DDoS attacks.
Requests are distributed among the servers by load balancers, so this
prevents server overload and guarantees efficient utilization. The next
generation of switches with high-bandwidth uplinks also enhances the
design by preparing it for future increasing traffic. While initial
setup costs and complexity are moderately high, the long-term
improvements in reliability, security, and performance justify the
investment.

**Proposed Design**

This updated network design topology will increase scalability and
reliability to further improve the performance of the e-commerce
website. The collapsed core layer introduces redundancy and high-speed
interconnections between network devices, ensuring uninterrupted
operations during high demand or equipment failure. This ensures
uninterrupted operation even through durations of excessive calls for or
equipment failure. Dual firewalls (Firewall1 and Firewall2) hook up with
multiple ISPs and twin routers (Router5 and Router6) for Internet
access. Provides robust load balancing competencies to make certain
non-stop availability. Multiple switches are used to efficaciously
distribute the community load on the access layer. Every server
Including web server utility Database server and storage server has a
dedicated backup server This ensures that vital services continue to be
functional in the event of hardware or software program failure.
Separation of various varieties of servers into unique regions (e.G.
Community, packages, safety, storage, and database server) facilitates
growth aid allocation and improves efficiency. Using interconnected
switches increases scalability. This allows the network to expand as
needed. Overall, the proposed layout correctly addresses the
restrictions of the preceding setup. By combining redundant resources
load balancing and particular backups collectively. These modifications
have been optimized to support the increasing needs of e-commerce
websites. Even all through rush hour and guarantees maximum efficiency

**Evaluation and Justification**

This design ensures reliability, scalability, and security while
addressing expected traffic spikes. Redundant core switches and backup
servers minimize downtime and enhance fault tolerance. VLANs logically
segment traffic and allocate bandwidth efficiently, maintaining quality
even during high loads. Firewalls and DDoS protection enhance security,
safeguarding data integrity and availability. Although the initial
investment is significant, the benefits---reliability, scalability, and
capacity to support business growth---outweigh the costs. The complexity
added by VLANs and multilayer switches are justified by the resulting
improvements in performance and scalability, ensuring the system meets
both current and future needs.

![image](https://github.com/user-attachments/assets/1ae05814-0608-417e-9cc1-b0df39da116f)
