# Post-Quantum Cryptography in GSMA 5G Telecommunications

This repository holds the research study and technical presentation developed for the Advanced Information Systems Security course at Politecnico di Torino (MSc in Cybersecurity).

## Executive Summary

Mobile network operators face a growing security challenge from quantum computing. Even before a full-scale cryptographically relevant quantum computer is built, attackers can execute Harvest Now, Decrypt Later (HNDL) attacks by recording encrypted 5G radio and core backhaul traffic today to decrypt it later.

This study examines the cryptographic primitives within the GSM Association (GSMA) architecture—specifically evaluating standard elliptic-curve Diffie-Hellman (ECDHE) key agreement in 5G-AKA and SUPI/SUCI subscriber privacy mechanisms. We propose a migration path to post-quantum cryptography based on NIST standards and the NSA Commercial National Security Algorithm Suite 2.0 (CNSA 2.0) timeline, balancing quantum resistance against latency and signaling overhead in mobile networks.

## Research Framework & Cryptographic Evaluation

Our methodology focused on three main areas:

- Threat Modeling: We analyzed the exposure of 5G Non-Standalone (NSA) and Standalone (SA) core network interfaces (N1, N2, N3, N32) to passive interception and long-term decryption risks.
- Candidate Algorithm Analysis: We evaluated NIST-selected post-quantum algorithms for telco environments:
  - ML-KEM (Kyber) for key encapsulation across radio control channels and TLS 1.3 backhaul links.
  - ML-DSA (Dilithium), SLH-DSA (SPHINCS+), and FN-DSA (FALCON) for authentication in eSIM provisioning and network function identity.
- Performance & Overhead Assessment: Larger public keys and ciphertexts introduce MTU fragmentation and radio signaling delays. We modeled these trade-offs for constrained SIM/eSIM secure elements and IoT endpoints, proposing hybrid KEM schemes (Curve25519 combined with ML-KEM) for smooth backward compatibility.

### Technologies & Standards Reference
- NIST Post-Quantum Cryptography Standardization Suite
- NSA CNSA 2.0 Guidelines
- 3GPP Technical Specifications (TS 33.501, TS 33.503)
- GSMA Security Specifications (FS.31, FS.34)

## Document Inspection & Verification

The primary artifact in this repository is the complete presentation deck (`GSMA_presentation.pdf`). 

To read the report locally on Linux:
```bash
xdg-open GSMA_presentation.pdf
```

You can verify the document checksum using:
```bash
sha256sum GSMA_presentation.pdf
```

## Authors

- Alessandro Giacconi
- Christian Chiappa
- Luca Ferretti

We acknowledge the technical specifications provided by the GSMA Post-Quantum Telco Network Taskforce and the Politecnico di Torino cybersecurity faculty for their feedback during our evaluation.
