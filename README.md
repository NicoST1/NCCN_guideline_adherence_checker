
# Machine Learning-based Clinical Decision Support System for Predicting and Enhancing Guideline Adherence in Breast cancer patients


## CDSS - Guideline Adherence

The CDSS uses Docker Compose to deploy an application consisting of three services: `app`, `db`, and `predictive_model`

### Prerequisites

- Docker Desktop (Windows, macOS) or Docker Engine and Docker Compose (Linux)

### Setup and Deployment

1. **Install Docker:**
   - Go to the Docker official website: https://www.docker.com/
   - Click on the "Get Started" button.
   - Download the appropriate Docker Desktop installer for your operating system (Windows, macOS).
   - Install Docker Desktop by following the on-screen instructions.

3. **Download the project files:**
   - Download the folder called `adherence_cdss`. It should contain the Docker Compose configuration file (docker-compose.yml) and necessary folders, like the MySQL custom folder.

2. **Start Docker Desktop**
   - Make sure that Docker Desktop is up and running.

4. **Open a terminal:**
   - Windows: Press `Win + R`, type `cmd`, and press Enter.
   - macOS: Press `Cmd + Space`, type `terminal`, and press Enter.
   - Linux: Press `Ctrl + Alt + T`.

5. **Navigate to the project directory in the terminal:**
   - Use the `cd` command followed by the path to the project folder. For example:
     ```
     cd /path/to/adherence_cdss
     ```

6. **Run the Docker Compose command:**
   - In the terminal, type the following command and press Enter:
     ```
     docker-compose up -d
     ```
   - Docker Compose will now download the required images, build the custom MySQL image, and start the services defined in the docker-compose.yml file. This process may take a few minutes to complete.

7. **Verify that the services are running:**
   - In the terminal, type the following command and press Enter:
     ```
     docker-compose ps
     ```
   - You should see a list of the three services (`app`, `db`, and `predictive_model`) with their current status. All services should have a "State" of "Up".


### Accessing and Using the Application

1. **Access the application:**
   - Open your web browser and visit the application at: http://localhost:8080

2. **Sign in:**
   - Use the following credentials to sign in:
     - Email: nicolas.st@nhs.com
     - Password: password

3. **Check guideline adherence for existing patients:**
   - To check guideline adherence for an existing patient, open their record by clicking on it on the patient table.
   - The guideline adherence results can be found at the bottom of the patient's details page.

4. **Edit patient details and recalculate adherence:**
   - If you edit the patient's details and save the changes, the guideline adherence will be recalculated automatically.

5. **View a non-adherent case:**
   - To see an example of a non-adherent case, search for the patient named "Miv" in the patient records.

6. **Add new patients:**
   - To add a new patient, click on the "Add Patient" button and fill out the required information.
   - After adding a new patient, the guideline adherence will be calculated automatically for the newly added patient.


### Potential Issues and Solutions

1. **Permission issues on Linux:**
   - If you're using Linux and encounter permission issues when running Docker commands, try adding `sudo` before the command. For example:
     ```
     sudo docker-compose up -d
     ```

2. **Port conflicts:**
   - If the services fail to start due to port conflicts, ensure that the required ports (8080, 3306, and 5001) are not being used by other applications. You can change the ports in the `docker-compose.yml` file if necessary.

3. **Docker Compose not found:**
   - If the terminal shows an error that the `docker-compose` command is not found, ensure that Docker Compose is installed correctly and that the installation directory is added to your system's PATH variable.

4. **Troubleshooting services:**
   - If any service does not start correctly or shows an error, you can check the logs for more information using the following command:
     ```
     docker-compose logs SERVICE_NAME
     ```
     Replace `SERVICE_NAME` with the name of the service you want to check (e.g., `app`, `db`, or `predictive_model`).




