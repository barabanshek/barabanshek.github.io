---
layout: page
title: Current Research
description: >
  Here you should be able to find everything you need to know to accomplish the most common tasks when blogging with Hydejack.
hide_description: true
sitemap: true
permalink: /current_research/
---

## Towards CPU-free datamovement in the cloud

<font size="4">  In my current work, I'm exploring new hardware and software technologies to enable <strong>fast</strong>, <strong>reliable</strong>, <strong>low-overhead</strong>, and <strong>secure</strong> communication in datacenters. I'm working towards designing of completely CPU-free cloud networking stacks, where the entire cross-machine application-to-application data path <em>runs outside of the processor, with zero software overhead and CPU utilization</em>. </font>


My general philosophy here is that datacenter processors should not waste their time and energy for data exchange. This is particularly important in the today's world of fine-granular, highly-concurrent, and interactive internet services, especially the ones based on the pay-as-you-go cost model. CPU-free communication stacks will dramatically reduce the total amount of CPU time required per application, and will also enable truly nano-second scale cloud networking. Just imagine your microservices where there is almost no difference in calling remote vs local functions. Physically, this is already possible today with all the advances in datacenter optical wiring and <a href="https://www.microsoft.com/en-us/research/project/sirius/" title="MSRC">switching</a>. We just needs to sort out the bottlenecks in the end-host, so here we go!
{:.note title="Philosophy"}

In addition to this main research direction, I recently started working (in collaboration with <a href="https://www.microsoft.com/en-us/research/group/azure-for-operators-afo-research/" title="MSRC">Microsoft Azure for Operators</a>) on cloud native 5G architectures and virtual radio access networks (vRAN). I'm still very new to this field, but I'm looking forward to the opportunities that 5G and vRAN open for low-latency communication and real-time in-network processing.

---

## Projects

##### <ins>Dagger: CPU-Free End-Host RPC Stack</ins>

<img src="../assets/img/dagger_nic.png" width="150" height="120" style="float:right" padding-top=10px />

In this project, we built the first proof-of-concept system for offloading a basic cloud RPC stack to cache-coherent FPGAs. Our FPGA-based SmartNIC runs the end-to-end RPC datapath in hardware, and communicates ready-to-use user-level objects **directly with the application memory** at low latency and high CPU efficiency. The latter is achieved via tight integration of the FPGA with the host processor over a NUMA interconnect. This essentially enables the shared-memory model of communication between applications and hardware, therefore bypassing the OS kernel, device drivers, and any other software layers. **Advisors**: <a href="https://www.csl.cornell.edu/~zhiruz/" title="Cornell">Professor Zhiru Zhang</a> and <a href="https://www.csl.cornell.edu/~delimitrou/" title="Cornell">Professor Christina Delimitrou</a>.

<a href="https://github.com/barabanshek/Dagger" title="MSRC">GitHub repo</a>

<a href="https://www.youtube.com/watch?v=ONnR6Mg6t4E" title="MSRC">ASPLOS'21 Conference Talk, 2021</a>

<a href="https://dl.acm.org/doi/abs/10.1145/3445814.3446696" title="MSRC">ASPLOS'21 Paper, 2021</a>

<a href="https://ieeexplore.ieee.org/document/9180035/" title="MSRC">IEEE CAL Early Work Paper, 2020</a>

##### <ins>Towards Virtual Radio Access Networks (vRAN) as Cloud Native Feature</ins>

<img src="../assets/img/5g.png" width="160" height="130" style="float:right" padding-top=2px />

5G networks come with great bandwidth and low latency, therefore enabling many emerging applications such as self-driving cars, drone swarms, IoT, cloud gaming, and so on at the large scale. However, in order to take the full advantage of their potential, networking functions for 5G and beyond must be scalable, reliable, and intelligently adaptable. This research aims to develop novel technologies to address the aforementioned requirements and enhance the widespread adoption of radio access networks. In particular, we further extend the concept of vRAN to introduce fault tolerance, disaggregation, and load balancing when deploying 5G network functions on the edge cloud platforms at scale. This project is a collaborative effort with <a href="https://www.microsoft.com/en-us/research/group/azure-for-operators-afo-research/" title="MSRC">Microsoft Azure for Operators</a> group at Microsoft. **Mentor:** <a href="http://anujkalia.com/" title="AnujKalia">Anuj Kalia</a>.


##### <ins>Efficient End-Host Networking with I/O-Optimized x86/64 ISA Extension</ins>

<img src="../assets/img/x86.png" width="140" height="110" style="float:right" padding-top=10px />

The upcoming (as of 2021) server-class x86/64 processors will come with the optimized I/O sub-system through a set of new ISA extensions. In this research, we evaluate the new I/O system on commodity and kernel-bypass end-host networking stacks, and estimate its potential to improve the performance and CPU efficiency of cloud networking. This project is being carried over with the generous support by <a href="https://www.intel.com/" title="Intel">Intel Corporation</a>.

