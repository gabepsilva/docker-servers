example:


docker run --name samba-server --restart unless-stopped -d -p 445:445 -v /mnt/adata/public/:/samba/public/ -v /mnt/adata/secure/:/samba/secure samba-server