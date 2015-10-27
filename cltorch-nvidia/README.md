To run this, you need:
- nvidia GPU compatible with 346.96 driver on the host
- nvidia 346.96 driver on the host (eg `nvidia-smi` should work, and should report driver version 346.96)
- run: `docker run -it  --device /dev/nvidiactl --device /dev/nvidia0 --device /dev/nvidia-uvm  hughperkins/cltorch-nvidia:346.96`

