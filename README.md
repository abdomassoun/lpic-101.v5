| **Package Manager** | **Search** | **Install** | **Remove** | **Update/Upgrade** | **List Installed** | **Show Package Info** | **Find File Owner** |
|---------------------|-----------|-------------|------------|---------------------|---------------------|----------------------|--------------------|
| **dpkg** | N/A | `dpkg -i <package>.deb` | `dpkg -r <package>` (remove, keep config) / `dpkg -P <package>` (purge) | N/A | `dpkg -l` | `dpkg -L <package>` | `dpkg -S <file>` |
| **apt-get** | `apt-cache search <keyword>` | `apt-get install -f <package>` | `apt-get remove <package>` (keep config) / `apt-get purge <package>` (purge config) | `apt-get update` (refresh list) / `apt-get upgrade` (upgrade all) | `apt list --installed` | `apt-cache show <package>` | `dpkg -S <file>` |
| **rpm** | `rpm -qa \| grep <package>` | `rpm -i <package>.rpm` | `rpm -e <package>` | N/A | `rpm -qa <package>` | `rpm -qi <package>` | `rpm -qf <file>` |
| **yum** | `yum search <package>` | `yum install <package>` | `yum remove <package>` | `yum update` `yum check-update <pacakge>` | `yum list installed` | `yum info <package>` | `yum whatprovides <file>` |
| **dnf** | `dnf search <package>` | `dnf install <package>` | `dnf remove <package>` | `dnf update` | `dnf list --installed` | `dnf info <package>` | `dnf provides <file>` |
| **zypper** | `zypper search <package>` `zypper se <package>` | `zypper install <package>` `zypper in <package>`| `zypper remove <package>` | `zypper refresh` | `zypper list installed` | `zypper info <package>` | `zypper se --provides <file>` |

| **Package Manager** | **Add Repository** | **Remove Repository** | **List Repositories** | **Enable/Disable Repository** |
|---------------------|------------------|------------------|------------------|------------------|
| **apt** | `add-apt-repository <repo>` / `echo 'deb <repo>' | tee /etc/apt/sources.list.d/<repo>.list` | `add-apt-repository --remove <repo>` / `rm /etc/apt/sources.list.d/<repo>.list` | `apt-cache policy` / `apt list --all-versions` | N/A |
| **yum** | `yum-config-manager --add-repo <repo>` | `yum-config-manager --remove <repo>` | `yum repolist all` | `yum-config-manager --enable <repo>` / `yum-config-manager --disable <repo>` / `yum-config-manager --enable updates` |
| **dnf** | `dnf config-manager --add-repo <repo>` | `dnf config-manager --remove <repo>` | `dnf repolist` | `dnf config-manager --set-enabled <repo>` / `dnf config-manager --set-disabled <repo>` |
| **zypper** | `zypper addrepo <repo> <alias>` | `zypper removerepo <alias>` | `zypper repos` | `zypper mr -e <alias>` / `zypper mr -d <alias>` |


| **Package Manager** | **Add Repository** | **Remove Repository** | **List Repositories** | **Enable/Disable Repository** | **Repository Configuration Path** |
|---------------------|------------------|------------------|------------------|------------------|------------------|
| **apt** | `add-apt-repository <repo>` / `echo 'deb <repo>'` | `tee /etc/apt/sources.list.d/<repo>.list` | `add-apt-repository --remove <repo>` / `rm /etc/apt/sources.list.d/<repo>.list` | `apt-cache policy` / `apt list --all-versions` | N/A | `/etc/apt/sources.list` and `/etc/apt/sources.list.d/` |
| **yum** | `yum-config-manager --add-repo <repo>` | `yum-config-manager --remove <repo>` | `yum repolist all` | `yum-config-manager --enable <repo>` / `yum-config-manager --disable <repo>` / `yum-config-manager --enable updates` | `/etc/yum.repos.d/` |
| **dnf** | `dnf config-manager --add-repo <repo>` | `dnf config-manager --remove <repo>` | `dnf repolist all` | `dnf config-manager --set-enabled <repo>` / `dnf config-manager --set-disabled <repo>` | `/etc/yum.repos.d/` |
| **zypper** | `zypper addrepo <repo> <alias>` | `zypper removerepo <alias>` | `zypper lr` | `zypper mr -e <alias>` / `zypper mr -d <alias>` | `/etc/zypp/repos.d/` |

| Option | `mkfs.ext4` / `mke2fs` | `mkfs.exfat` | `mkfs.fat` | `mkfs.xfs` |
|---------|----------------|------------|------------|------------|
| **`-b SIZE`** | 1024, 2048, 4096 bytes. | ❌ | ❌ | 512–65536 bytes (default 4096). |
| **`-c`** | ✅ | ❌ | ✅ | ❌ |
| **`-C FILENAME BLOCK_COUNT`** | ❌ | ❌ | ✅ | ❌ |
| **`-d DIRECTORY`** | ✅ | ❌ | ❌ | ❌ |
| **`-F`** | ✅ | ❌ | ❌ | ✅ |
| **`-F SIZE`** | ❌ | ❌ | ✅ | ❌ |
| **`-i VOL_ID`** | ❌ | ✅ | ❌ | ❌ |
| **`-L LABEL`** | Max 16 chars. | Max 15 chars. | Max 11 chars. | Max 12 chars. |
| **`-m crc=VALUE`** | ❌ | ❌ | ❌ | ✅ |
| **`-m uuid=VALUE`** | ❌ | ❌ | ❌ | ✅ |
| **`-n NAME`** | ❌ | Max 15 chars. | Max 11 chars. | ❌ |
| **`-N`** | ❌ | ❌ | ❌ | ✅ |
| **`-p SECTOR`** | ❌ | ✅ | ❌ | ❌ |
| **`-q`** | ❌ | ❌ | ❌ | ✅ |
| **`-s SECTORS`** | ❌ | ✅ | ❌ | ❌ |
| **`-U ID`** | ✅ | ❌ | ❌ | ❌ |
| **`-v`** | ❌ | ❌ | ✅ | ❌ |
| **`-l logdev=DEVICE`** | ❌ | ❌ | ❌ | ✅ |
| **`-l size=VALUE`** | ❌ | ❌ | ❌ | ✅ |

| **Symbol**  | **Description** | **Example** | **Usage** |
|-------------|-----------------|-------------|-----------|
| `>`         | Redirects stdout (overwrite) | `ls > output.txt` | Writes command output to a file, overwriting it. |
| `>>`        | Redirects stdout (append) | `echo "Hello" >> file.txt` | Appends output to an existing file. |
| `<`         | Redirects stdin from a file | `sort < file.txt` | Reads input from a file instead of the keyboard. |
| `2>`        | Redirects stderr (overwrite) | `ls /fakepath 2> error.txt` | Saves error messages to a file, overwriting it. |
| `2>>`       | Redirects stderr (append) | `ls /fakepath 2>> error.log` | Appends error messages to a file. |
| `&>`        | Redirects stdout & stderr (overwrite) | `command &> output.txt` | Saves both output and errors to a file. |
| `2>&1`      | Merges stderr into stdout | `command > file.txt 2>&1` | Combines both outputs into one file. |
| `|`         | Pipe: Sends stdout of one command to stdin of another | `ls -l | less` | Passes data between commands. |
| `tee`       | Sends output to both a file and stdout | `ls | tee file.txt` | Saves output to a file while displaying it. |
| `/dev/null` | Discards output (black hole) | `command > /dev/null 2>&1` | Runs a command but ignores all output. |
| `<<`        | **Here-document**: Multi-line input | `cat <<EOF`<br>`Hello`<br>`World`<br>`EOF` | Redirects multiple lines of input to a command. |
| `<<<`       | **Here-string**: Single-line input | `grep "pattern" <<< "search this line"` | Passes a string directly as stdin to a command. |

| **Symbol**  | **Description** | **Example** | **Usage** |
|-------------|-----------------|-------------|-----------|
| `>`         | Redirects stdout (overwrite) | `ls > output.txt` | Writes command output to a file, overwriting it. |
| `>>`        | Redirects stdout (append) | `echo "Hello" >> file.txt` | Appends output to an existing file. |
| `<`         | Redirects stdin from a file | `sort < file.txt` | Reads input from a file instead of the keyboard. |
| `2>`        | Redirects stderr (overwrite) | `ls /fakepath 2> error.txt` | Saves error messages to a file, overwriting it. |
| `2>>`       | Redirects stderr (append) | `ls /fakepath 2>> error.log` | Appends error messages to a file. |
| `&>`        | Redirects stdout & stderr (overwrite) | `command &> output.txt` | Saves both output and errors to a file. |
| `2>&1`      | Merges stderr into stdout | `command > file.txt 2>&1` | Combines both outputs into one file. |
| `|`         | Pipe: Sends stdout of one command to stdin of another | `ls -l | less` | Passes data between commands. |
| `tee`       | Sends output to both a file and stdout | `ls | tee file.txt` | Saves output to a file while displaying it. |
| `/dev/null` | Discards output (black hole) | `command > /dev/null 2>&1` | Runs a command but ignores all output. |
| `<<`        | **Here-document**: Multi-line input | `cat <<EOF`<br>`Hello`<br>`World`<br>`EOF` | Redirects multiple lines of input to a command. |
| `<<<`       | **Here-string**: Single-line input | `grep "pattern" <<< "search this line"` | Passes a string directly as stdin to a command. |


### **Summary of GRUB 2 Installation and Configuration**

#### **Installing GRUB 2**
- Use `grub-install` to install GRUB 2.
- If the system is unbootable, use a Live CD or rescue disc.
- Identify the boot partition using `fdisk -l /dev/sda`. The boot partition is marked with `*` under the "Boot" column.
- Mount the boot partition:
  ```sh
  mkdir /mnt/tmp
  mount /dev/sda1 /mnt/tmp
  ```
- Install GRUB on the boot device:
  - If a dedicated boot partition exists:
    ```sh
    grub-install --boot-directory=/mnt/tmp /dev/sda
    ```
  - If `/boot` is within the root filesystem:
    ```sh
    grub-install --boot-directory=/boot /dev/sda
    ```

#### **Configuring GRUB 2**
- The main configuration file is `/boot/grub/grub.cfg` (auto-generated).
- Edit `/etc/default/grub` and apply changes with:
  ```sh
  update-grub
  ```
  (equivalent to `grub-mkconfig -o /boot/grub/grub.cfg`).
- Key GRUB options:
  - `GRUB_DEFAULT=`: Sets the default menu entry.
  - `GRUB_TIMEOUT=`: Time before auto-booting the default entry.
  - `GRUB_CMDLINE_LINUX=`: Adds kernel parameters.
  - `GRUB_ENABLE_CRYPTODISK=`: Enables encrypted disk support.

#### **Managing GRUB Menu Entries**
- Custom entries are added in `/etc/grub.d/40_custom`.
- Example menu entry:
  ```sh
  menuentry "Default OS" {
      set root=(hd0,1)
      linux /vmlinuz root=/dev/sda1 ro quiet splash
      initrd /initrd.img
  }
  ```
- Disk and partitions are numbered from `0` in GRUB (`hd0,1` = `sda1`).

#### **Finding and Using UUIDs**
- Get filesystem UUIDs with:
  ```sh
  ls -l /dev/disk/by-uuid/
  ```
- Use UUID in GRUB:
  ```sh
  search --set=root --fs-uuid <UUID>
  ```

#### **Interacting with GRUB 2**
- Use arrow keys to select a boot entry.
- If only a countdown is shown, press `Shift` to reveal the menu.

### **Summary of GRUB Legacy Installation and Configuration**

#### **Installing GRUB Legacy from a Running System**
- Use `grub-install` to install GRUB Legacy:
  ```sh
  grub-install /dev/sda
  ```
- **Important:** Install GRUB on the disk (e.g., `/dev/sda`), not a partition (`/dev/sda1`).
- By default, GRUB files are copied to `/boot`. To specify a different location:
  ```sh
  grub-install --boot-directory=/mnt/boot /dev/sda
  ```

#### **Installing GRUB Legacy from a GRUB Shell**
- If the system is unbootable, access the GRUB shell (`grub>` prompt) and set the boot partition:
  ```sh
  grub> root (hd0,0)
  ```
- To find the `/boot` partition:
  ```sh
  grub> find /boot/grub/stage1
  ```
- Install GRUB to the MBR:
  ```sh
  grub> setup (hd0)
  ```
- Reboot to apply changes.

#### **Configuring GRUB Legacy Menu Entries**
- GRUB Legacy configuration is stored in `/boot/grub/menu.lst`.
- A typical Linux entry:
  ```sh
  title My Linux Distribution
  root (hd0,0)
  kernel /vmlinuz root=/dev/hda1
  initrd /initrd.img
  ```
- **Key points:**
  - `title`: Displayed in the boot menu.
  - `root`: Specifies the boot partition.
  - `kernel`: Loads the kernel.
  - `initrd`: Loads the initial RAM disk (if needed).

#### **Loading Additional Modules**
- GRUB Legacy supports extra modules stored in `/boot/grub/i386-pc/`.
- Example of loading a module:
  ```sh
  module /boot/grub/i386-pc/915resolution.mod
  ```
  (Used for Intel 800/900 series graphics.)

#### **Chainloading Other Operating Systems (e.g., Windows)**
- GRUB Legacy supports chainloading for systems like Windows.
- Example configuration:
  ```sh
  title Windows XP
  root (hd0,1)
  makeactive
  chainload +1
  boot
  ```
- **Key parameters:**
  - `root (hd0,1)`: Specifies the Windows boot partition.
  - `makeactive`: Marks the partition as active.
  - `chainload +1`: Loads the bootloader from the first sector of the partition.
  - `boot`: Starts the selected OS.
