## How It Works

### 1. Script Overview  
The script creates two **systemd services**:  
- **Startup Service**: Runs `caspida start-all` during system boot.  
- **Shutdown Service**: Executes `caspida stop-all` during system shutdown or reboot.  

### 2. Key Features  
- Ensures **clean transitions** for Caspida components.  
- Automates repetitive tasks, reducing the risk of **human error**.  
- Simple integration with **systemd** for seamless operation.

---

## Steps to Use the Script  

### 1. Create the Script File  
Run the following command to create the script file:  
```bash
sudo vi /home/caspida/setup_caspida_boot.sh
```
Paste the script code into the editor, save, and exit.

---

### 2. Make the Script Executable  
Make the script executable by running:  
```bash
sudo chmod +x /root/setup_caspida_boot.sh
```

---

### 3. Run the Script as Root  
Execute the script with root privileges:  
```bash
sudo /root/setup_caspida_boot.sh
```

---

## What This Script Does  

- Creates **startup and shutdown scripts** in `/usr/local/bin`.  
- Sets the appropriate **permissions** for these scripts to be executable.  
- Creates **systemd service files** for both startup and shutdown.  
- Reloads the systemd daemon and enables the services for automatic execution.

---

## Verification  

After running the script, check the status of the services to ensure they are active:  
```bash
sudo systemctl status caspida_startup.service
sudo systemctl status caspida_shutdown.service
```

---

## Test Reboot and Shutdown  

### 1. Reboot Test  
Reboot the server to confirm the **startup service** works as expected:  
```bash
sudo reboot
```

### 
On system shutdown, the **shutdown service** will automatically run to stop Caspida gracefully.

--- 
