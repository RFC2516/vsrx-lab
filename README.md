# Containerlab Web-Filtering lab using vSRX3.0

This is a repository I created to teach myself web-filtering on the vSRX3.0 image in preparation for the JNCIA-SEC exam. I have provided all necessary images complete the lab **EXCEPT** for the Juniper vSRX 3.0 22.4R1.10 image. Which must be obtained from Juniper's website. After obtaining the image you may use the [vrnetlab](https://containerlab.dev/manual/vrnetlab/) project to containerize it.

# Quick Start Guidance

1. [Install Containerlab](https://containerlab.dev/install/)

`bash -c "$(curl -sL https://get.containerlab.dev)"`

2. Download the vSRX image

https://support.juniper.net/support/downloads/?f=srx, ensure that you download the 22.4R1.10 KVM image with sha1 checksum 1bfbf97e7acb84f6ae371d39b87570191d6a715d.

3. Containerize the image

`git clone https://github.com/hellt/vrnetlab.git`
`cd vrnetlab/vsrx/`
`mv /path/to/your/vsrx/image/junos-vsrx3-x86-64-22.4R1.10.qcow2 .`
`make`

4. Start the lab

`cd ~`
`git clone https://github.com/RFC2516/vsrx-lab.git`
`cd vsrx-lab/`
`clab dep -t topology.yaml`

# Troubleshooting any containerlab errors

Your local output should match the following:

```
root@localhost:# which docker
/usr/bin/docker
```

```
root@localhost:# which containerlab
/usr/bin/containerlab
```

```
root@localhost:# docker images | grep vsrx
vrnetlab/vr-vsrx                            22.4R1.10    <docker-id>   4 weeks ago     1.73GB
```

```
root@localhost:# tree
.
├── dhcpd.conf
├── topology.yaml
└── vsrx1.conf

0 directories, 3 files
root@localhost:#
```