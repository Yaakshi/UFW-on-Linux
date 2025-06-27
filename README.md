# UFW-on-Linux

## Basic firewall management skills and understanding of network traffic filtering

1. Verify the status of UFW.
```sudo ufw status```

![image](https://github.com/user-attachments/assets/e204cfe9-825d-41d4-8dfe-e9260cc69cd8)

2. Enable UFW and verify status again.
```sudo ufw enable```

![image](https://github.com/user-attachments/assets/06e8b898-49f7-4516-b630-e4425e783c8a)

Note: Login as root to avoid using sudo in every command.

3. Learn more about UFW
```man ufw```

![image](https://github.com/user-attachments/assets/28ed8e7d-3bd5-4079-8f00-b5120dedd637)

```ufw -h```

![image](https://github.com/user-attachments/assets/2deac2f9-e126-400c-86f7-7e22c2cac1d7)

4. List the RULES

```ufw status numbered```

![image](https://github.com/user-attachments/assets/ef17bdb3-4a10-404f-8e71-c4455a4ec150)

Looks like there are no rules setup initially.

6. Let us try some rules

- Add a rule to block inbound traffic on port 23 (Telnet)

```ufw deny 23```

![image](https://github.com/user-attachments/assets/af63af7f-5e0b-46a7-9d03-79549dde23a5)

- Add a rule to block inbound traffic on port 80 (HTTP)

```ufw deny 80```

![image](https://github.com/user-attachments/assets/d801604c-7c5a-4ac6-8ac8-8c440e166e13)

- If we try to access a HTTP website, we will be able to view the webpage.
  
- Add a rule to block outbound traffic to port 80 (HTTP)

```ufw deny out 80```

![image](https://github.com/user-attachments/assets/e85655a1-9e00-495c-90a4-6f1eb00c725e)

- If we try to access the same website now, the browser will not load it or will throw error message.

- Add a rule to allow inbound traffic on port 22 (SSH)

```ufw allow 22```

![image](https://github.com/user-attachments/assets/30bf7f2f-15f4-46e2-af50-8d5f4622cddd)

- Delete the rules to block outbound traffic to port 80 (HTTP)
  
```ufw delete 3```
```ufw delete 7```

![image](https://github.com/user-attachments/assets/30dd13cf-cac5-4a05-9a24-81b2d8533a04)

- After deleting the rules that blocks the traffic to port 80, now we will be able to access the website normally.













