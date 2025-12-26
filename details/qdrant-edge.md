# Qdrant Edge

**Category:** Vector Database Engines  
**Website:** https://qdrant.tech/edge/  
**Vendor:** Qdrant  
**Deployment:** Embedded / on-device / edge environments  
**Status:** Private beta

Qdrant Edge is a lightweight, in-process vector search engine optimized for embedded devices, autonomous systems, and mobile/edge agents. It enables on-device, low-latency vector retrieval with a small memory footprint and optional synchronization with Qdrant Cloud.

---

## Features

### Architecture & Deployment
- **In-process vector search engine**
  - Runs as a library embedded directly into the application process.
  - No separate database service, no background threads, no runtime daemons.
  - Suitable for mobile apps, robots, and embedded systems where extra services are undesirable.

- **Local-first operation**
  - Retrieval and search run fully on-device and offline.
  - Designed for environments with intermittent or limited connectivity.

- **Optional Qdrant Cloud synchronization**
  - Can sync with Qdrant Cloud only when needed.
  - Supports use cases such as:
    - Data transfer between edge and cloud.
    - Promoting edge data to cloud tenants.
    - Coordinating large-scale or distributed deployments.

### Performance & Resource Utilization
- **Optimized for low-memory, low-compute hardware**
  - Tailored to resource-constrained devices (embedded boards, low-power CPUs, etc.).
  - No idle overhead from extra processes or background services.

- **Memory efficiency & compression**
  - Built-in compression options to reduce memory footprint.
  - Ability to offload data to disk to further conserve RAM.

### Search Capabilities
- **Native vector search on-device**
  - Real-time vector retrieval for edge AI workloads.
  - Suitable for latency-sensitive applications running directly at the edge.

- **Hybrid & multimodal search**
  - Supports dense vectors and multimodal embeddings.
  - Handles embeddings from:
    - Text
    - Images
    - Audio
    - Sensor-derived data (e.g., LiDAR, radar, other signals)

- **Structured filtering**
  - Combines vector similarity search with filters on structured payload fields.
  - Enables more precise retrieval based on both semantics and metadata.

### Multitenancy & Workload Management
- **Edge-scale multitenancy**
  - Supports payload-based and shard-based tenant isolation.
  - Enables multiple logical tenants or datasets to coexist on constrained devices.

- **Query routing across uneven workloads**
  - Can route queries across tenants/shards to balance differing edge workloads.

### SDKs & Platform Support
- **Native SDKs for major edge platforms**
  - Java SDK for Android.
  - Swift SDK for Apple platforms.
  - Additional SDKs planned or available for other environments.

### Target Use Cases (On-Device AI)
- **Robotics & autonomy**
  - Multimodal retrieval from onboard sensors (e.g., LiDAR, radar, other robotic sensors).
  - Supports real-time decision-making and perception directly on the robot or autonomous system.

*(The site implies broader use across mobile agents and embedded AI systems, but only partially listed examples are included here.)*

---

## Pricing

- Not specified on the referenced content.  
- Qdrant Edge is currently described as a **private beta**; access and pricing details are not publicly listed and likely require direct contact with Qdrant.
