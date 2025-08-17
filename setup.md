# VirtualBox Installation
> Step-by-step instructions for installing VirtualBox on your host machine.

1. Download the latest version of **VirtualBox** from [virtualbox.org](https://www.virtualbox.org/).
2. Install VirtualBox using default installation settings.
3. *(Optional)* Install the Extension Pack for additional USB and network features.
4. Verify VirtualBox is working by launching it from the desktop/start menu.

---

# Kali Linux Setup
> Instructions for importing and configuring Kali Linux in VirtualBox.

1. Download the Kali Linux VirtualBox image from [kali.org](https://www.kali.org).
2. Open VirtualBox → **File → Import Appliance**, then select the `.ova` file.
3. Start the VM and log in using the default credentials:

    ```text
    Username: kali  
    Password: kali
    ```

4. Update Kali tools:

    ```bash
    sudo apt update && sudo apt upgrade -y
    ```

---

# Metasploitable2 Setup
> Instructions for importing and configuring Metasploitable2 in VirtualBox.

1. Download the Metasploitable2 VirtualBox image from the official Rapid7 source.
2. Extract the `.zip` file and import the VM into VirtualBox.
3. Start the VM.
4. Default credentials:

    ```text
    Username: msfadmin  
    Password: msfadmin
    ```

---

# Networking Configuration (Host-Only Adapter)
> Setup instructions for connecting Kali Linux and Metasploitable2 in an isolated network.

1. Shut down both Kali and Metasploitable2 VMs.
2. In VirtualBox, go to **Preferences → Network → Host-Only Networks**.
3. Verify that a Host-Only network exists (e.g. `vboxnet0`). If not, create one.
4. Configure Kali Linux network:
   - Go to **Settings → Network → Adapter 1**
   - Set **Attached to**: *Host-Only Adapter*
5. Repeat the same settings for Metasploitable2.
6. Start both VMs.
7. Verify connectivity:

    **On Kali:**

    ```bash
    ip addr
    ping <192.168.56.102>
    ```

    **On Metasploitable2:**

    ```bash
    ifconfig
    ping <192.168.56.101>
    ```
