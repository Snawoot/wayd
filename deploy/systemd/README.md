1. Place file `wayd.service` into `~/.config/systemd/user` directory.
2. Adjust path to shell script in `wayd.service` unit file.
3. `systemctl --user daemon-reload`
4. `systemctl --user start wayd.service`
5. `systemctl --user enable wayd.service`
6. Check logs with `journalctl --user -u wayd.service`
