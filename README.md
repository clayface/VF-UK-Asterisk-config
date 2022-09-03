These files are provided as a template to allow users to connect to Vodafone UK's VoIP network. Please modify to suit your username, password, provided proxy server and client.

Note that a firewall rule should also be added to permit inbound UDP traffic to port 5065, ideally only from IPs used by Vodafone. Alternatively, the `qualify_frequency` option may be used to prevent a UDP connection timeout. Note that this timeout will vary between devices.

If running on a local network behind NAT, you may need to enable SIP ALG on the router, if such option is available, otherwise it will not be possible to make or receive calls. If the option is not available or you experience issues with calls, you will need to enable the `external_media_address` and `external_signalling_address` options in pjsip.conf, with both of these set to your public IP address. In such a case, obtaining a static IP from Vodafone would be advised.

If experiencing any issues, please check that your router is not modifying the TOS values. Packets without correct values will be dropped. If behind NAT, please ensure that the router is not modifying the source port of outbound packets, as only ports 5065 and 10000-10010 are accepted for signalling and RTP respectively.
