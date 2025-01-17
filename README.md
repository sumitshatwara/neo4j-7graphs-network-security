# Neo4j Network & Security Graph Demo Setup Guide

This guide provides step-by-step instructions to set up and run a Neo4j-powered Network & Security Graph Demo using Neo4j AuraDB or Neo4j Desktop. It includes dataset import, schema setup, and visualization using Neo4j Bloom.

---

## Prerequisites

### Hardware & OS Requirements

#### Neo4j AuraDB
- A modern web browser.
- No special local hardware requirements.

#### Neo4j Desktop
- At least **8-16GB RAM** and **4 CPU cores**.
- **~20GB free disk space** for local data storage.
- Supported Operating Systems: **Windows**, **macOS**, or **Linux**.

### Software Requirements
- **Neo4j AuraDB**: A valid AuraDB instance or access to create one.
- **Neo4j Desktop**: Download version 5.x from the [Neo4j Download Center](https://neo4j.com/download/).

### Neo4j Bloom
- **AuraDB**: Bloom is included in Professional and Enterprise tiers.
- **Neo4j Desktop**: Bloom can be installed as a plugin.

### Credentials and Data Files
Ensure you have the following files:
- `Bloom Perspective.json`: Preconfigured Bloom perspective.
- `neo4j-5x-dump.tar`: Neo4j 5.x Database dump


---

## 1. Environment Setup

1. Create a working directory:   
```
(bash) mkdir ~/neo4j-demo && cd ~/neo4j-demo
```
Place the following files into this directory:
```
Bloom Perspective.json
neo4j-5x-dump.tar
```
## 2. Neo4j AuraDS Setup (Option A)

- Create an AuraDS Instance
- Go to the Neo4j Aura Console.
- Create a new AuraDS Enterprise instance and choose the appropriate tier (Free, Professional, or Enterprise).
- Connect to AuraDS
- Note the neo4j+s://<your-instance-connection-string> URL, username, and password.
- Open the Neo4j Query Brower by clicking “Query” under Tools section of the Left Panel in the Aura console.
- Load Data into AuraDS using "Restore from backup file" option under Inpect dropdown of the AuraDS instance

## 3. Neo4j Desktop Setup (Option B)
- Install Neo4j Desktop
- Download and install Neo4j Desktop from the [Neo4j Download Center](https://neo4j.com/download/).
- Launch Neo4j Desktop and create a new local database project.
- Create a New Graph Database
- Click Add Graph > Local DBMS, and choose Neo4j 5.x.
- Set a password for the neo4j user.
- Import a Database Dump (Local Only)
- Stop the database if it's running.
- Navigate to the database folder:
- Click the three dots on the DBMS card > Open folder > Installation.
- Restore the dump using neo4j-admin using Terminal option of DBMS:
```
neo4j-admin database restore neo4j --from=neo4j_database.dump --force
```
- Start the Database
- Start the DBMS in Neo4j Desktop.
- Open Neo4j Browser and connect using your credentials.

## 4. Neo4j Bloom and GDS Installation and Configuration

### AuraDB
- Access Bloom on Aura Console.
- Click the Explore icon in Tools section of the left panel of Aura console.
- GDS option will be available directly from Bloom.

### Neo4j Desktop
- Go to the Plugins tab in Neo4j Desktop.
- Install Neo4j Bloom and Graph Data Science plugin.
- Restart the database and open Bloom.
  
## 5. Loading the Bloom Perspective
- In Bloom, click the gear icon (Perspectives) > Import Perspective.
- Select ```Bloom Perspective.json```.
- Set the imported perspective as active.
  
## 6. LLM Agent RAG Solution Schema Overview on NeoConverse
- Review the schema creation script (NeoConverse LLM Agent Schema.docx).
- Launch the [NeoConverse web app](https://neoconverse.graphapp.io/) on browser
- Click on "Add Agent" on the left panel.
- Add the General information, database connection details and credentials of AuraDS instance or Neo4j Desktop DB instance.
- Select AI Service, Add Key and Model name under Gen AI API option.
- Copy paste the schema the document (NeoConverse LLM Agent Schema.docx)
- Add the Few Shot examples from the same document.
- Ask example questions mentioned in the document.



