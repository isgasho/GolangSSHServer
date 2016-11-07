# GolangSSHServer
A standalone SSH server written in Go

# Usage
1. Generate keys
ssh-keygen -t ed25519 -f ./authkey
ssh-keygen -t ed25519 -f ./hostkey

2. Replace keys in the code
cat authkey.pub      Find "authPublicKeys" variable in the code and replace the example key that's already there. 
cat hostkey          Find "hostKeyBytes" variable in the code and replace the example key that's already there

3. Recompile
go install github.com/leechristensen/GolangSSHServer

4. Run the SSH server
GolangSSHServer 2222           Starts the SSH server on localhost:2222
GolangSSHServer 0.0.0.0:2222   Starts the SSH server on 0.0.0.0:2222

5. Connect to the SSH server with your SSH client + authentication key
ssh -i authkey user@localhost