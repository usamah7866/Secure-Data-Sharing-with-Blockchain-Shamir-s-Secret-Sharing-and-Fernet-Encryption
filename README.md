# Secure Data Sharing with Blockchain, Shamir’s Secret Sharing, and Fernet Encryption

This repository contains the implementation of a **secure and distributed data sharing system** that combines:

- **Blockchain (simulated)** for transaction recording and traceability  
- **Shamir’s Secret Sharing** for robust distributed key management  
- **Fernet symmetric encryption** for strong data confidentiality  

The approach is based on the paper:  
*Secure and Distributed Data Sharing with Blockchain and Shamir’s Secret Sharing*  
by Usama Habib and Ayad Mashaan Turky.

---

## 📌 Features
- **Data Fragmentation**: Splits data into multiple fragments before encryption.  
- **Fernet Encryption**: Encrypts each fragment with a unique symmetric key.  
- **Key Sharing with SSS**: Splits encryption keys into multiple shares; a threshold number of shares is required for reconstruction.  
- **Blockchain Simulation**: Records metadata (fragment IDs, share locations, hashes) to ensure immutability and traceability.  
- **Encryption & Decryption Pipelines**: End-to-end workflow for secure storage and retrieval.  

---

## ⚙️ Methodology
The methodology is divided into two main stages:  

### 🔒 Encryption
1. **Data Fragment Generation** – Sensor/data readings are split into smaller fragments.  
2. **Data Encryption** – Each fragment is encrypted using **Fernet**.  
3. **Key Sharing** – Encryption keys are split into shares using **Shamir’s Secret Sharing**.  
4. **Key Storage** – Shares are distributed into separate storage folders.  
5. **Blockchain Recording** – A simulated blockchain stores transaction metadata (fragment ID, shares, locations).  

### 🔑 Decryption
1. **Transaction Retrieval** – Fetch metadata about the encrypted fragment and its shares.  
2. **Key Reconstruction** – Rebuild the original key using Shamir’s Secret Sharing.  
3. **Encrypted Data Retrieval** – Load the fragment from storage.  
4. **Data Decryption** – Recover the original data using the reconstructed key.  

---

## 🛠️ Tech Stack
- **Python 3.10+**
- Libraries:
  - `cryptography` (Fernet encryption/decryption)  
  - `pycoin` (Shamir’s Secret Sharing)  
  - `secrets`, `random`, `os`, `datetime`, `json`  


📌 Future Work

Integration with real blockchain networks (e.g., Ethereum, Hyperledger).

Support for large datasets with optimized fragmentation strategies.

Implementation of user authentication and authorization.
