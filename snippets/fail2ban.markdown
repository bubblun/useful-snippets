# fail2ban

## How to unblock IP from fail2ban

Log onto the server and `su –` to root

To see what IPs are blocked type the following:

    iptables -L -n

This will output the iptables list and at the bottom you will see the Chain fail2ban-SSH

    Chain fail2ban-SSH (1 references)
    target prot opt source destination
    RETURN all -- 0.0.0.0/0 0.0.0.0/0

To remove the customer's IP from the block list type the following:

    iptables -D fail2ban-SSH -s IP -j DROP

Switch the IP with the customer's public IP address.

This will remove the user from the block list and they should be able to access the dedicated server.
