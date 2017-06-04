# command_notifier
Send notification after command execution
```
sudo add-apt-repository ppa:leolik/leolik
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install libnotify-bin
pkill notify-osd

sudo add-apt-repository ppa:nilarimogard/webupd8
sudo apt-get update
sudo apt-get install notifyosdconfig
```
PROMPT_COMMAND="history | tac | awk 'NR == 1' | cut -d' ' -f4- | xargs -I{} notify-send $(pwd) {}"
// Ошибка заключается в том что $(pwd) выполняется в момент присвоения. Вместо этого стоило бы использовать read var1 < <(pwd) 
