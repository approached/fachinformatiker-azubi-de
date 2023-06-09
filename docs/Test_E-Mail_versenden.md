---
title: Test E-Mail versenden
---

# Test E-Mail versenden

Es gibt verschiedene Tools um aus der Komandozeile Test E-Mails zu
versenden.

## Tool: mail

Mit dem folgende Command kann man eine Testmail versenden:

`apt-get install mailutils`
`mail -s "Test Email" user@example.com < /dev/null`

Oder *systemlog* als Anhang und Inhalttext versenden:

`mail -a /var/log/syslog -s "Syslog File" user@example.com < /var/log/syslog`

Oder bestimmten Text mit einem Absender versenden:

`echo "Hello World" | mail -r from@example.com -s "Test Email" user@example.com`

## Tool: Ssmtp

Das Paket **Ssmtp** dient als MTA *Mail Transfer Agent* und die Aufgabe
ist lediglich Mails zu verschicken.

1.  <https://linuxundich.de/gnu-linux/system-mails-ohne-einen-mail-server-mit-ssmtp-verschicken/>

## Notes

-   <https://unix.stackexchange.com/questions/36982/can-i-set-up-system-mail-to-use-an-external-smtp-server>
