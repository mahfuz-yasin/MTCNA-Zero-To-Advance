
# 🖥️ GNS3 Setup & MikroTik Router Basic Configuration

## 🔑 Login Info

* **Username**: `admin`
* **Password**: (খালি রাখুন)
* **Ctrl + C** → Password Skip করতে

---

## 📌 Interface Check

```bash
interface print
# অথবা
interface/print
```

---

## 📌 Assign IP Address

```bash
ip address add address=192.168.0.1/24 interface=ether1
```

---

## 📌 Show IP Address

```bash
ip address print
```

---

## ❗ Problem: একই Interface-এ একাধিক IP দিলে Conflict হয়

**Solution:**

1. অতিরিক্ত IP মুছে ফেলুন

   ```bash
   ip address remove <row-number>
   ```
2. অথবা ভুল Interface-এ দেওয়া হলে Edit করুন

   ```bash
   ip address edit <row-number>
   ```

---

## 📌 Edit IP Address / Configuration

```bash
ip address edit <row-number>
# Enter চাপলে Editing Mode আসবে
# উদাহরণ:
# value-name: interface
# ether2 দিয়ে Replace করুন
# Save করুন CTRL + O
# Quit করতে CTRL + X
```

---

## 📌 Remove IP Address

```bash
ip address remove <row-number>
```

---

# ⚙️ MikroTik Basic Configuration (Step by Step)

### Step 01: WAN Configure \[ISP]

```bash
ip address add address=100.0.0.2/30 interface=ether1
```

### Step 02: LAN Configure \[Local Users]

```bash
ip address add address=192.168.0.1/24 interface=ether2
```

### Step 03: Default Route Configure

```bash
ip route add gateway=100.0.0.1
```

### Step 04: NAT Configure

```bash
ip firewall nat add chain=srcnat action=masquerade out-interface=ether1
```

### Step 05: DNS Setup

```bash
ip dns set servers=8.8.8.8,8.8.4.4 allow-remote-requests=yes
```

---

## 📌 Bonus Commands

### Check Internet Connectivity

```bash
ping 8.8.8.8
```

### Show Routes

```bash
ip route print
```

### Save Configuration

```bash
system backup save name=config_backup
```

---

✅ এভাবে করলে আপনার MikroTik Router (GNS3-তে) **ISP (WAN) → Router → LAN Users** এর জন্য Basic Internet Access পাবে।

---

## ** Daigram : **

<img width="1196" height="629" alt="Image" src="https://github.com/user-attachments/assets/049c6351-9d93-4980-a312-6c32f594a48f" />