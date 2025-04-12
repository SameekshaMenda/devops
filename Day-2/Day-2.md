#  Create EC2 Instance on AWS & Connect via PuTTY

This guide walks you through setting up an EC2 instance on AWS and connecting to it from a Windows machine using **PuTTY**.

---

##  Prerequisites

- An [AWS account](https://aws.amazon.com/)
- Installed:
  - [PuTTY](https://www.putty.org/)
  - [PuTTYgen](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)

---

##  Step 1: Launching an EC2 Instance

1. Go to the [AWS Console](https://console.aws.amazon.com/)
2. Navigate to **EC2 > Instances**
3. Click **Launch Instance**
4. **Configure:**
   - **Name**: `MyInstance`
   - **AMI**: Choose `Amazon Linux 2 AMI` or `Ubuntu`
   - **Instance Type**: `t2.micro` (Free tier eligible)
   - **Key Pair**:
     - Click “Create new key pair”
     - Name: `my-key`
     - Type: `RSA`, Format: `.pem`
     - Click “Create Key Pair” (save `.pem` file safely!)
   - **Network Settings**:
     - Allow SSH (port 22)
5. Click **Launch Instance**

---

##  Step 2: Convert `.pem` to `.ppk` using PuTTYgen

PuTTY does not support `.pem`, so we need to convert it to `.ppk`.

1. Open **PuTTYgen**
2. Click **Load**
3. Change file type to `All Files (*.*)`
4. Select your `.pem` file (e.g., `my-key.pem`)
5. Click **Open**, then click **Save private key**
6. Save it as `my-key.ppk` (you can skip the passphrase)


---

## 💻 Step 3: Connect via PuTTY

1. Open **PuTTY**
2. In **Host Name**, type:
- Replace `<Public IPv4 DNS>` with your instance's public DNS or IP (found in AWS EC2 dashboard)

3. In the left menu:
- Go to **Connection > SSH > Auth**
- Click **Browse**, and select your `my-key.ppk` file

4. (Optional) Go to **Session** → Save your session with a name for future use
5. Click **Open**
6. If prompted with a security alert, click **Yes**
7. You’re now connected to your EC2 instance via PuTTY! 🎉

---
