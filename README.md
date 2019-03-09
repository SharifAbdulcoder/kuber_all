# kuber_all


kops create cluster --name="terrakops.com" --zone $ZONES --node-size $NODE_SIZE --master-size $MASTER_SIZE --master-zones $ZONES --networking weave --topology private --bastion=true --dns private --yes


kops create cluster --name terrakops.com --state="s3://terrakops.com" --zones="us-east-2b,us-east-2a,us-east-2c"  --master-zones="us-east-2b,us-east-2a,us-east-2c" --node-count=2 --node-size="t2.micro" --master-size="t2.micro"   --networking="weave" --topology="private" --dns="private" --yes  


Suggestions:
 * validate cluster: kops validate cluster
 * list nodes: kubectl get nodes --show-labels
 * ssh to the master: ssh -i ~/.ssh/id_rsa admin@api.terrakops.com
 * the admin user is specific to Debian. If not using Debian please use the appropriate user based on your OS.
 * read about installing addons at: https://github.com/kubernetes/kops/blob/master/docs/addons.md.
