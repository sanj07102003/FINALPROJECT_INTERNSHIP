QDRANT DOCUMENTATION 

comprehensive guide to setting up and using Qdrant in Python with Docker 

Step 1: Install Docker Desktop on Windows 10

[1]Download Docker Desktop:

[2]Visit the Docker Desktop for Windows page.

[3]Click on "Download for Windows" to get the installer.

[4]Install Docker Desktop:

[5]Run the downloaded installer.

[6]Follow the on-screen instructions to complete the installation.

[7]Ensure that the option to use WSL 2 (Windows Subsystem for Linux) is selected during installation for optimal performance.

[8]Start Docker Desktop:

[9]Launch Docker Desktop from the Start menu.

[10]Wait for Docker to initialize; the Docker icon in the system tray will indicate when it's ready.

Verify Installation:

Open PowerShell or Command Prompt.

Run:

docker --version

You should see the Docker version information, confirming a successful installation.

Step 2: Run Qdrant with Docker

Pull the Qdrant Docker Image:

In PowerShell or Command Prompt, execute:

docker pull qdrant/qdrant

Run the Qdrant Container:

Choose a directory on your system to store Qdrant data, e.g., C:\qdrant\data.

Run the container with:

docker run -d --name qdrant -p 6333:6333 -v C:\qdrant\data:/qdrant/storage qdrant/qdrant

NOTE:

-d: Runs the container in detached mode.

--name qdrant: Names the container "qdrant".

-p 6333:6333: Maps port 6333 of the container to port 6333 on your host.

-v C:\qdrant\data:/qdrant/storage: Mounts the host directory C:\qdrant\data to the container's /qdrant/storage directory for data persistence.

Verify the Qdrant Container is Running:

docker ps

Look for a container named "qdrant" in the list.

Step 3: Install the Qdrant Python Client

Set Up a Python Environment:

Ensure Python is installed on your system. If not, download and install it from the official Python website.
It's recommended to use a virtual environment:

python -m venv qdrant-env
cd qdrant-env
.\Scripts\activate

Install the Qdrant Client:

With the virtual environment activated, run:

pip install qdrant-client

Step 4: Connect to Qdrant in Python

Create a Python Script:

Create a file named qdrant_setup.py with the following content

Run the Script:

Execute:

python qdrant_setup.py

You should see output indicating the existing collections (likely empty initially).

Step 5: Create a Collection and Insert Vectors

Extend the Python Script:

Update qdrant_setup.py to include collection creation and vector insertion:

Run the Script:

Execute:

python qdrant_setup.py

This will create a collection named "my_collection" and insert 5 random 128-dimensional vectors.

Step 6: Perform a Vector Search

Update the Python Script:

Add a search function to qdrant_setup.py:

Run the Script:

Execute:

python qdrant_setup.py

This will perform a search with a random query vector and display the top 2 closest vectors from the collection.

