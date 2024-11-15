# IIT Delhi Proxy

(Copied from https://compiler.ai/dev/proxy.html)

## Accessing internet on server machine
Server machines do not have direct internet connection and, like other department machines, you need to login into proxy server before you can access internet. The following steps show how to login into proxy server using the iitd-login.py script.

As the server is shared by many users, we advise that you remain logged-in into proxy server only while you need internet connection and disconnect as soon as possible.

## HOWTO login into proxy server without GUI using iitd-login.py script
1. Setup environment variables for your proxy server. For e.g., for PhD students http_proxy (and friends) need to be set to http://proxy61.iitd.ac.in:3128. For cstaff members, the server is http://proxy21.iitd.ac.in:3128.
- The exhaustive list of variables is: http_proxy, https_proxy, HTTP_PROXY, HTTPS_PROXY.
2. Download the iitd-login.py script and copy it to your home directory.
3. In the script, change PROXY_BASE_URL to the URL for your proxy (for e.g., it is proxy61.iitd.ac.in for PhD students).
4. Start a tmux session: tmux
5. Launch the login script: env -u http_proxy -u https_proxy -u HTTP_PROXY -u HTTPS_PROXY python3 iitd-login.py -d
6. Provide credentials
7. On success, the message "Logged in." will be printed (along with other messages).
8. Detach from the tmux session using C-b d (Ctrl+B followed by d)
9. Do your git pull etc.
10. Attach to tmux session with tmux a
11. Hit C-c to logout from proxy server.
12. Exit from shell to close tmux session.
