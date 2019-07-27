# Alpine Linux EC2 AMIs

**These are not official AWS or Alpine images.  They are community built and
supported.**

These AMIs should work with most EC2 features such as Elastic Network Adapters
and NVMe EBS volumes.  If you find any problems launching them on current
generation instances, please open an [issue](https://github.com/mcrute/alpine-ec2-ami/issues)
and include as much detailed information as possible.

During the *first boot* of instances created with these AMIs, the lightweight
[tiny-ec2-bootstrap](https://github.com/mcrute/tiny-ec2-bootstrap) init
script...
- sets the instance's hostname,
- installs the SSH authorized_keys for the 'alpine' user,
- disables 'root' and 'alpine' users' passwords,
- expands the root partition to use all available EBS volume space,
- and executes a "user data" script (must be a shell script that starts with `#!`)

If you launch these AMIs to build other images (via [Packer](https://packer.io),
etc.), don't forget to remove `/var/lib/cloud/.bootstrap-complete` --
otherwise, instances launched from those second-generation AMIs will not run
`tiny-ec2-bootstrap` on their first boot.

The more popular [cloud-init](https://cloudinit.readthedocs.io/en/latest/)
is currently not supported on Alpine Linux.  If `cloud-init` support is
important to you, please open an [issue](https://github.com/mcrute/alpine-ec2-ami/issues).

## AMIs

### Alpine Linux 3.10.1 (2019-07-26)
<details><summary><i>click to show/hide</i></summary><p>

| Region | alpine-ami-3.10.1-x86_64-r1 |
| ------ | --- |
| ap-northeast-1 | [ami-0adeee26a46805278](https://ap-northeast-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0adeee26a46805278) ([launch](https://ap-northeast-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0adeee26a46805278)) |
| ap-northeast-2 | [ami-06637cd011ec49efa](https://ap-northeast-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-06637cd011ec49efa) ([launch](https://ap-northeast-2.console.aws.amazon.com/ec2/home#launchAmi=ami-06637cd011ec49efa)) |
| ap-south-1 | [ami-09e1bd549945283a2](https://ap-south-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-09e1bd549945283a2) ([launch](https://ap-south-1.console.aws.amazon.com/ec2/home#launchAmi=ami-09e1bd549945283a2)) |
| ap-southeast-1 | [ami-081de8e0c4d9e28e5](https://ap-southeast-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-081de8e0c4d9e28e5) ([launch](https://ap-southeast-1.console.aws.amazon.com/ec2/home#launchAmi=ami-081de8e0c4d9e28e5)) |
| ap-southeast-2 | [ami-0e2c774fdc1d38ba1](https://ap-southeast-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0e2c774fdc1d38ba1) ([launch](https://ap-southeast-2.console.aws.amazon.com/ec2/home#launchAmi=ami-0e2c774fdc1d38ba1)) |
| ca-central-1 | [ami-02fed61c453469d90](https://ca-central-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-02fed61c453469d90) ([launch](https://ca-central-1.console.aws.amazon.com/ec2/home#launchAmi=ami-02fed61c453469d90)) |
| eu-central-1 | [ami-0659cf3939d5818e6](https://eu-central-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0659cf3939d5818e6) ([launch](https://eu-central-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0659cf3939d5818e6)) |
| eu-north-1 | [ami-0859a31a742c902ed](https://eu-north-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0859a31a742c902ed) ([launch](https://eu-north-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0859a31a742c902ed)) |
| eu-west-1 | [ami-00fcd74ef57d7f27d](https://eu-west-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-00fcd74ef57d7f27d) ([launch](https://eu-west-1.console.aws.amazon.com/ec2/home#launchAmi=ami-00fcd74ef57d7f27d)) |
| eu-west-2 | [ami-06e36c52d4a7c245a](https://eu-west-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-06e36c52d4a7c245a) ([launch](https://eu-west-2.console.aws.amazon.com/ec2/home#launchAmi=ami-06e36c52d4a7c245a)) |
| eu-west-3 | [ami-06a5559ce996d5bac](https://eu-west-3.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-06a5559ce996d5bac) ([launch](https://eu-west-3.console.aws.amazon.com/ec2/home#launchAmi=ami-06a5559ce996d5bac)) |
| sa-east-1 | [ami-0087fd3ce3d62d34d](https://sa-east-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0087fd3ce3d62d34d) ([launch](https://sa-east-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0087fd3ce3d62d34d)) |
| us-east-1 | [ami-063929a9ea787ced6](https://us-east-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-063929a9ea787ced6) ([launch](https://us-east-1.console.aws.amazon.com/ec2/home#launchAmi=ami-063929a9ea787ced6)) |
| us-east-2 | [ami-0a5ef71ab2deee8fd](https://us-east-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0a5ef71ab2deee8fd) ([launch](https://us-east-2.console.aws.amazon.com/ec2/home#launchAmi=ami-0a5ef71ab2deee8fd)) |
| us-west-1 | [ami-04165aa967c5fb241](https://us-west-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-04165aa967c5fb241) ([launch](https://us-west-1.console.aws.amazon.com/ec2/home#launchAmi=ami-04165aa967c5fb241)) |
| us-west-2 | [ami-08147c2b1a80b44c4](https://us-west-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-08147c2b1a80b44c4) ([launch](https://us-west-2.console.aws.amazon.com/ec2/home#launchAmi=ami-08147c2b1a80b44c4)) |

</p></details>

### Alpine Linux 3.9.4 (2019-07-26)
<details><summary><i>click to show/hide</i></summary><p>

| Region | alpine-ami-3.9.4-x86_64-r1 |
| ------ | --- |
| ap-northeast-1 | [ami-0d12649cf98b9c29b](https://ap-northeast-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0d12649cf98b9c29b) ([launch](https://ap-northeast-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0d12649cf98b9c29b)) |
| ap-northeast-2 | [ami-004372232cf1a20ac](https://ap-northeast-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-004372232cf1a20ac) ([launch](https://ap-northeast-2.console.aws.amazon.com/ec2/home#launchAmi=ami-004372232cf1a20ac)) |
| ap-south-1 | [ami-091de53a3582f2779](https://ap-south-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-091de53a3582f2779) ([launch](https://ap-south-1.console.aws.amazon.com/ec2/home#launchAmi=ami-091de53a3582f2779)) |
| ap-southeast-1 | [ami-07f6f363322b884d5](https://ap-southeast-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-07f6f363322b884d5) ([launch](https://ap-southeast-1.console.aws.amazon.com/ec2/home#launchAmi=ami-07f6f363322b884d5)) |
| ap-southeast-2 | [ami-0eeff0d7c1943665c](https://ap-southeast-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0eeff0d7c1943665c) ([launch](https://ap-southeast-2.console.aws.amazon.com/ec2/home#launchAmi=ami-0eeff0d7c1943665c)) |
| ca-central-1 | [ami-011ad5e9b2fcfa1d5](https://ca-central-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-011ad5e9b2fcfa1d5) ([launch](https://ca-central-1.console.aws.amazon.com/ec2/home#launchAmi=ami-011ad5e9b2fcfa1d5)) |
| eu-central-1 | [ami-0d4f6bb2a4f857256](https://eu-central-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0d4f6bb2a4f857256) ([launch](https://eu-central-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0d4f6bb2a4f857256)) |
| eu-north-1 | [ami-01c04b1d21717da2d](https://eu-north-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-01c04b1d21717da2d) ([launch](https://eu-north-1.console.aws.amazon.com/ec2/home#launchAmi=ami-01c04b1d21717da2d)) |
| eu-west-1 | [ami-0c9ac6e4570bad5c1](https://eu-west-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0c9ac6e4570bad5c1) ([launch](https://eu-west-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0c9ac6e4570bad5c1)) |
| eu-west-2 | [ami-0bc07c10c240525e4](https://eu-west-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0bc07c10c240525e4) ([launch](https://eu-west-2.console.aws.amazon.com/ec2/home#launchAmi=ami-0bc07c10c240525e4)) |
| eu-west-3 | [ami-0ebda60768a596a7f](https://eu-west-3.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0ebda60768a596a7f) ([launch](https://eu-west-3.console.aws.amazon.com/ec2/home#launchAmi=ami-0ebda60768a596a7f)) |
| sa-east-1 | [ami-0a2d4fb282401447a](https://sa-east-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0a2d4fb282401447a) ([launch](https://sa-east-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0a2d4fb282401447a)) |
| us-east-1 | [ami-0a8b8edcf88c2e496](https://us-east-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0a8b8edcf88c2e496) ([launch](https://us-east-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0a8b8edcf88c2e496)) |
| us-east-2 | [ami-030ce78952c4c097c](https://us-east-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-030ce78952c4c097c) ([launch](https://us-east-2.console.aws.amazon.com/ec2/home#launchAmi=ami-030ce78952c4c097c)) |
| us-west-1 | [ami-0e27a7d83365f16be](https://us-west-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0e27a7d83365f16be) ([launch](https://us-west-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0e27a7d83365f16be)) |
| us-west-2 | [ami-07f10e32e0621a4eb](https://us-west-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-07f10e32e0621a4eb) ([launch](https://us-west-2.console.aws.amazon.com/ec2/home#launchAmi=ami-07f10e32e0621a4eb)) |

</p></details>

### Alpine Linux Edge (2019-07-26)
<details><summary><i>click to show/hide</i></summary><p>

| Region | alpine-ami-edge-x86_64-r1 |
| ------ | --- |
| ap-northeast-1 | [ami-0bf33aa7c22d9baa2](https://ap-northeast-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0bf33aa7c22d9baa2) ([launch](https://ap-northeast-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0bf33aa7c22d9baa2)) |
| ap-northeast-2 | [ami-0c70ff6aa9e968c53](https://ap-northeast-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0c70ff6aa9e968c53) ([launch](https://ap-northeast-2.console.aws.amazon.com/ec2/home#launchAmi=ami-0c70ff6aa9e968c53)) |
| ap-south-1 | [ami-00837ab20c320f641](https://ap-south-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-00837ab20c320f641) ([launch](https://ap-south-1.console.aws.amazon.com/ec2/home#launchAmi=ami-00837ab20c320f641)) |
| ap-southeast-1 | [ami-0d62bf83d0ae6b478](https://ap-southeast-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0d62bf83d0ae6b478) ([launch](https://ap-southeast-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0d62bf83d0ae6b478)) |
| ap-southeast-2 | [ami-0534b78492e708ad8](https://ap-southeast-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0534b78492e708ad8) ([launch](https://ap-southeast-2.console.aws.amazon.com/ec2/home#launchAmi=ami-0534b78492e708ad8)) |
| ca-central-1 | [ami-0fbcb246fd84682da](https://ca-central-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0fbcb246fd84682da) ([launch](https://ca-central-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0fbcb246fd84682da)) |
| eu-central-1 | [ami-0b922ce94b41883a0](https://eu-central-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0b922ce94b41883a0) ([launch](https://eu-central-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0b922ce94b41883a0)) |
| eu-north-1 | [ami-04620f1f6b8407f65](https://eu-north-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-04620f1f6b8407f65) ([launch](https://eu-north-1.console.aws.amazon.com/ec2/home#launchAmi=ami-04620f1f6b8407f65)) |
| eu-west-1 | [ami-0cc1b66070b640f01](https://eu-west-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0cc1b66070b640f01) ([launch](https://eu-west-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0cc1b66070b640f01)) |
| eu-west-2 | [ami-09baff4c00e3e0ce2](https://eu-west-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-09baff4c00e3e0ce2) ([launch](https://eu-west-2.console.aws.amazon.com/ec2/home#launchAmi=ami-09baff4c00e3e0ce2)) |
| eu-west-3 | [ami-0f3788c21dfe04c22](https://eu-west-3.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0f3788c21dfe04c22) ([launch](https://eu-west-3.console.aws.amazon.com/ec2/home#launchAmi=ami-0f3788c21dfe04c22)) |
| sa-east-1 | [ami-079c7b7aa0d0ee0a1](https://sa-east-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-079c7b7aa0d0ee0a1) ([launch](https://sa-east-1.console.aws.amazon.com/ec2/home#launchAmi=ami-079c7b7aa0d0ee0a1)) |
| us-east-1 | [ami-0acf9e7ac49698b80](https://us-east-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0acf9e7ac49698b80) ([launch](https://us-east-1.console.aws.amazon.com/ec2/home#launchAmi=ami-0acf9e7ac49698b80)) |
| us-east-2 | [ami-094fc92fddc3a3be2](https://us-east-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-094fc92fddc3a3be2) ([launch](https://us-east-2.console.aws.amazon.com/ec2/home#launchAmi=ami-094fc92fddc3a3be2)) |
| us-west-1 | [ami-09d5e6573daf78927](https://us-west-1.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-09d5e6573daf78927) ([launch](https://us-west-1.console.aws.amazon.com/ec2/home#launchAmi=ami-09d5e6573daf78927)) |
| us-west-2 | [ami-0708c17fb90521af2](https://us-west-2.console.aws.amazon.com/ec2/home#Images:visibility=public-images;imageId=ami-0708c17fb90521af2) ([launch](https://us-west-2.console.aws.amazon.com/ec2/home#launchAmi=ami-0708c17fb90521af2)) |

</p></details>
