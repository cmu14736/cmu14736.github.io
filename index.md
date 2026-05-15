---
layout: default
---

# Distributed Systems: Techniques, Infrastructure, & Services

14-736 is a graduate-level distributed systems course offered by the [Information Networking Institute](https://www.cmu.edu/ini) at [Carnegie Mellon University](https://www.cmu.edu/).

### Course Description

Distributed computing is the foundation of modern Internet and cloud services and an enabling technology for many web, mobile, and embedded applications. This course explores foundational concepts of distributed computing systems, such as networked communication, coordinating time, consensus, impossibility of agreement, fault tolerance, and distributed storage, as well as system design concepts, such as trade-offs between performance, fault tolerance, complexity, and cost. Exploration of these topics includes significant project work in creating tools for distributed interaction, implementing practical algorithms, and prototyping scalable and fault-tolerant distributed systems.

### Learning Objectives

In taking and completing this course, students will:
* Gain a deep understanding of foundational concepts of distributed system design, implementation, and operation including concurrency, consistency, fault tolerance, consensus, and availability;
* Develop, test, and evaluate techniques for asynchronous, concurrent system operation while avoiding common mistakes that lead to system failure or outage;
* Gain hands-on experience in designing, developing, and testing protocols and applications for distributed systems using common programming methods.


### Lab Assignments

Labs are the primary component of the 14-736 course and the basis for the majority of the course learning objectives. Labs can be done individually or with a partner, using starter code templates made available by the course staff via GitHub, and lab deliverables are submitted using a custom Github integration.

The course includes a total of five lab assignments, most of which are done in the Go programming language with the possible exception of the final project. Brief descriptions of these labs are included here, while further information is made available only to students enrolled in the course.

* <details><summary>Lab 0: Multiplayer Game Server</summary><p>The goal of this lab is to provide practice and/or review of important programming concepts and primitives that future labs will depend on. This lab also helps to establish and strengthen Go programming skills. Students create a multiplayer game server that hosts multiple concurrent games and multiple remote clients that may be involved in any number of games simultaneously.  Successful completion of the lab allows students to practice and demonstrate familiarity with multi-threading, complex state management, concurrency, remote interaction over network sockets, and state machine implementation.</p></details>

* <details><summary>Lab 1: Remote Object Library</summary><p>The goal of this lab is to build a generic library that allows a developer to easily implement concurrent interactions with object instances stored on remote servers, similar to Java's concept of remote method invocation (RMI) or stateful remote procedure calls (RPC). The `remote` library provides functionality for both caller/client- and callee/server-side operations, where each ingests a simple interface specification detailing the available remote call types and names. Complete implementations of the remote calls are only needed on the server side, while the library encapsulates all network interaction internally, making client-side calls nearly identical to local calls. Successful completion of the lab allows students to practice and demonstrate familiarity with reflection, socket programming, message encoding and decoding, and development using the libary.</p></details>

* <details><summary>Lab 2: Raft Consensus Protocol</summary><p>The goal of this lab is to implement the Raft consensus protocol in Go using the `remote` library from Lab 1 for all server-to-server messaging and interaction between servers and the provided testing suite.  In this implementation, each Raft server stores an indefinite sequence of log entries (each a sequence of bytes), which will eventually be committed to an identical replicated log held by each server.  To balance effort with other labs, this lab does not require students to implement persistence, cluster membership changes, or log compaction/snapshots.  However, the implementation is intended to be practically useful in supporting a wide variety of possible services and systems. Successful completion of the lab allows students to practice and demonstrate expertise in multithreading, concurrency, race conditions, fault tolerance, and complex debugging.</p></details>

* <details><summary>Clustered Storage System</summary><p>The goal of this lab is to build a functional storage system using the `remote` and `raft` impelementations from previous labs, again interacting with a provided testing suite.  The specific system is a hybrid between a distributed hash table (DHT) and a distributed file system (DFS), as it includes a hierarchical directory structure with the potential to house an independent key-value store in each directory.  Each independent key-value store is managed by a group of cluster participants using a Raft instance, meaning that each system participant may belong to multiple independent Raft instances and correctly manage which instance manages which directories' contents.  In addition, each cluster participant exposes an HTTP-based client interface that multiplexes several API endpoints onto an HTTP server exposed on a single port.  When a client wants to perform an action involving a particular directory and/or key, it must interact with the participant containing the Raft leader in the group managing that particular key-value store.  Successful completion of the lab allows students to gain experience with a complex system architecture using multiple different types of interfaces and protocols, using multiple inter-dependent components across a virtualized cluster of servers, and management of detailed system configuration and state in fault scenarios.</p></details>

* <details><summary>Lab 4: Build Your Own System</summary><p>This final lab provides an opportunity for end-to-end design of a complex distributed system, including designing the desired functionality and interaction, specifying software and performance requirements, developing a testing suite to validate an implementation against the specified requirements, and implementing the proposed design in a way that passes all of the developed tests.  This lab may build on previously developed capabilities or build on open-source software, as long as no points are earned from any of these existing components (i.e., they can be used as enablers or tools), and any programming language and/or framework can be used. Students are required to submit a detailed proposal, that must be approved in writing by the instructor.</p></details>


### Code Management & Testing Infrastructure

This course uses GitHub to initialize and maintain students' code repositories for the labs.  In addition, there is an external testing service that interacts with student repositories using the GitHub API. This service is used as an auto-grader for all grade components based on testing, while all documentation components are graded manually by the course staff.

### Questions and Contact

Please direct questions about the 14-736 course to [Patrick Tague](mailto:tague@cmu.edu).

