# NotANormalWordpress
This is an ansible role that will launch a kubernetes cluster over AWS cloud and then it will launch deployments to deploy a multi-tier web application wordpress and integrate with MySQL and expose it over the public network.

1. Download all the files and keep it in a folder  `roles`.
2. Try to keep the `.pem` security key file in the same roles folder where you kept this repo files.
3. In `vars.yml`, replace your access key and secret key of AMI with mine.
4. change the values of variable instead of `image_id`.
5. Configure the `ansible.cfg` file according to your paths of `roles` directory.
6. All done! Just run `ec2.yml` file with : `ansible-playbook ec2.yml`.
7. Then, after successfully starting the instances and inventory updates. Run `main.yml` file with : `ansible-playbook main.yml`.
8. They will call the roles and apply the changes accordingly.

`This cluster will create two slave nodes and one master node for cluster. It contains the static inventory, you can practice the same with dynamic inventory too`
9. There is a YAML file `cred.yml` that will create two deployments one for `Wordpress` and another deployment for `MySQL` and a NodePort service that will expose the wordpress deployment to the outer world.
10. Make sure your security group allows all traffic to your EC2 instance, then only the pods running on them can be accessed.
11. Try to open the url in your browser: `<public-ip-of-your-master-node-ec2-instance>:<nodePort>` which is `30400` in my `cred.yml` file.

`Enjoy the wordpress application after installing it.`
