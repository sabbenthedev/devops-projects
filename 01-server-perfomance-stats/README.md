# server-stats.sh

a lightweight, no-bullshit bash script that gives you a quick health check of your Linux server. No complex parsing, no heavy third-party monitoring tools—just native commands that get the job done out of the box.

## what it does

the script runs in your terminal and prints a clean report covering:
- **system & uptime:** current uptime, and load averages.
- **active users & security:** who is currently logged in and recent failed login attempts.
- **cpu usage:** overall system cpu utilization.
- **memory usage:** total, used, and free RAM including percentages.
- **disk usage:** storage breakdown for your root partition.
- **top processes:** the top 5 resource-hogging processes by CPU and memory.

## stack

- **bash / shell scripting:**

## portability

built to run on almost any standard Linux server (Ubuntu, Debian, RHEL, CentOS, etc.) without installing extra packages.

*(Note: reading failed login attempts via `lastb` requires root privileges (`sudo`). On some modern distros or minimal setups where `lastb` / `/var/log/btmp` isn't available or active, it might not return output, but the script handles it cleanly without crashing).*

## how to run

make the script executable and run it with root privileges:

```bash
chmod +x server-stats.sh
sudo ./server-stats.sh
