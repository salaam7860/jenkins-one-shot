## Jenkins Terms Explained

### **Discard old builds**  
Automatically remove old builds from the system to free up space.

### **GitHub project**  
Connect this Jenkins project to a GitHub repository, allowing automatic version control and integration.

### **This project is parameterized**  
Allow users to provide custom inputs when starting a build. This makes the build process more flexible.

### **Throttle builds**  
Limit how often builds can happen to avoid overloading the system with too many builds at once.

### **Execute concurrent builds if necessary**  
Allow multiple builds of the same job to run at the same time to improve efficiency.

---

## Advanced Settings

### **Source Code Management**  
Manage and connect your code repository to Jenkins so it can automatically pull the latest code for builds.

- **None**: No source code management.
- **Git**: Use Git to manage your code repository.

### **Triggers**  
Set up actions to automatically start builds based on specific events like code changes or at scheduled times.

- **Trigger builds remotely (e.g., from scripts)**: Start a build from external scripts or requests.
- **Build after other projects are built**: Start a build after another project’s build finishes.
- **Build periodically**: Set a schedule to run builds at specific times (e.g., every night at midnight).
- **GitHub hook trigger for GIT SCM polling**: Trigger a build when GitHub sends a notification about code changes.
- **Poll SCM**: Regularly check for changes in the source code repository to trigger builds.

### **Environment**  
Set up environment variables and configurations that define how and where builds run (like credentials and file paths).

- **Delete workspace before build starts**: Clean up the workspace before starting a new build.
- **Use secret text(s) or file(s)**: Use secrets (like passwords or API keys) securely in your build process.
- **Add timestamps to the Console Output**: Add time information to the build logs.
- **Inspect build log for published build scans**: View detailed information from build scans.
- **Terminate a build if it's stuck**: Automatically stop builds if they take too long to prevent them from running indefinitely.
- **With Ant**: Run builds using Apache Ant, a tool for automating tasks like compiling code.

---

## Build Steps  
Automate the build process with ordered tasks, such as compiling code, running tests, and deploying the application.

- **Add build step**: Add a task that runs during the build, like compiling code or running tests.

---

## Post-build Actions  
Define actions that happen after a build completes, like sending notifications, saving build results, or triggering other builds.

- **Add post-build action**: Add an action that occurs after a build, such as sending notifications or saving build artifacts.

---

## Save  
Save all your configurations for the Jenkins project.
