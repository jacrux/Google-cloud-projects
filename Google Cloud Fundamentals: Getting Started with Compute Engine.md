# Google-cloud-projects
# Google Cloud Fundamentals: Getting Started with Compute Engine
1. Create a Compute Engine virtual machine using the Google Cloud Platform (GCP) Console.

        gcloud compute instances create my-vm-1 -- machine-type "n1-standard-1" --image-project "debian-cloud --image "debian-9-stretch-v20190213" --subnet "default" --tags http
        gcloud compute firewall-rules create allow-http --action=ALLOW --destination=INGRESS  --rules=http:80 --taret-tags=http
2. Create a Compute Engine virtual machine using the gcloud command-line interface.


        gcloud config set compute/zone us-central1-b
        gcloud compute instances create "my-vm-2" --machine-type "n1-standard-1" --image-project "debian-cloud" --image "debian-9-stretch-v20190213" --subnet "default"
        
3. Connect between the two instances

- Use the ping command to confirm that my-vm-2 can reach my-vm-1 over the network 
- Connect to my-vm-2:
   
        gcloud compute ssh my-vm-2

 - ping my-vm-1 from my-vm-2
 
        ping -c 4 my-vm-1
        
        ping my-vm-1
- Use the ssh command to open a command prompt on my-vm-1

        ssh my-vm-1
        
- At the command prompt on my-vm-1, install the Nginx web server

        sudo apt-get install nginx-light -y

sudo nano /var/www/html/index.nginx-debian.html

Hi from Jide

curl http://localhost/


exit

curl http://my-vm-1/

gcloud compute instances list
