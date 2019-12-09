# scalemate-systemd
Systemd service for Scalemate

This repo contains file to create a systemd service for scalemate. Scalemate allows publish custom memory and socket metrics to AWS Cloudwatch. This can be useful when adding memory metric alarms to trigger autoscaling of an ASG.

To deploy the service you need to do the following.

You would need to deploy scalemate following the guide from the scalemate repo.

```https://github.com/eladnava/scalemate```

To setup the scalemate systemd service. Follow the steps below.

```
sudo cp scalemate /usr/bin/

sudo chmod +x /usr/bin/scalemate

sudo cp scalemate.service /lib/systemd/system/scalemate.service

sudo cp /lib/systemd/system/scalemate.service /etc/systemd/system/scalemate.service

sudo chmod 644 /etc/systemd/system/scalemate.service

sudo systemctl enable scalemate.service

sudo systemctl start scalemate.service

sudo systemctl status scalemate.service

```

If you are having issues starting the service troubleshoot with journalctl using the command below.


``` sudo journalctl -xe ```




