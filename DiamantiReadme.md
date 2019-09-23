The following command can be used to create a rootfs for diamanti specific forks

script -fec 'sudo -E GOPATH=$GOPATH AGENT_INIT=yes USE_DOCKER=true GO_AGENT_PKG=github.com/diamanticom/agent AGENT_SOURCE_BIN=$GOPATH/src/github.com/kata-containers/agent/kata-agent AGENT_VERSION=vlan_enpoint SECCOMP=no ./rootfs.sh clearlinux '

Now, build initrd using the commands in the repo readme.md. Also, change configuration.toml to use initrd and not image.

Snippet:

[hypervisor.qemu]
#image=/usr/share/kata-containers/kata-containers.img
initrd=/usr/share/kata-containers/kata-containers-initrd.img


