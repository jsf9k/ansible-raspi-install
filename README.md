# ansible-araspi-install #

An Ansible playbook to help get a Raspberry Pi up and running.

## Usage ##

After booting from a stock [Raspian Buster
Lite](https://www.raspberrypi.org/downloads/raspbian/) SD card, you
will need to:
1. Use `vi` (with `sudo`) to edit the file `/etc/ssh/sshd_config` by
   changing the `ChallengeResponseAuthentication` setting to `yes`.
2. Restart the ssh service using `sudo systemctl restart ssh`.
3. Generate a hash for the password to be used on your personal
   account using `mkpasswd --method=sha-512`.

At this point we can populate `inventory.yml` and any group or host
variables files and run `site.yml`:

```console
ansible-playbook -i inventory.yml site.yml
```

At this point your new Raspberry Pi is ready to be configured.  The
project [jsf9k/ansible-home](https://github.com/jsf9k/ansible-home)
can be used for this purpose.
