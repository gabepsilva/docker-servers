FROM alpine

RUN apk --no-cache --no-progress upgrade
RUN apk --no-cache --no-progress add bash samba

RUN mkdir -p /samba/secure/
RUN mkdir -p /samba/public/
RUN chmod 0777 /samba/public/
RUN chown -R nobody:nogroup /samba/public/

COPY smb.conf /etc/samba/smb.conf

RUN (echo badpass; echo badpass) | smbpasswd -a -s root

EXPOSE 445

CMD ["smbd", "--foreground", "--log-stdout", "--no-process-group"] 



