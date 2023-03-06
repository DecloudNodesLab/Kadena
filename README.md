<div align="center">

<p align="center"><img src="https://user-images.githubusercontent.com/23629420/219872517-2adc32b1-5f64-4d48-9a81-1e2ef6b01a53.png" width=90% </p>

# Kadena node on Akash Network

</div>

___

<div align="center">
  
| [Twitter Decloud Nodes Lab](https://twitter.com/NodesLab) |
|:--:|

| [Akash Network](https://akash.network/) | [Forum Akash Network](https://forum.akash.network/) | [Kadena](http://kadena.io/) |
|:--:|:--:|:--:|
___

Our news channels and technical support:

| [Discord Akash Network](https://discord.akash.network/) | [Telegram Akash Network](https://t.me/AkashNW) |  [Twitter Akash Network](https://twitter.com/akashnet_)
|:--:|:--:|:--:|
  
  
| [Discord Kadena](https://discord.com/invite/bsUcWmX) | [Telegram Kadena](https://t.me/kadena_io) | [Twitter Kadena](https://twitter.com/kadena_io)
|:--:|:--:|:--:|

| [Инструкция на русском](/README_RU.md) |
|:--:|
</div>

___

## Node deployment
Open [WEB interface](https://deploy.cloudmos.io/) `Cloudmos`.

Make sure you have **more than 6 AKT** on your balance and **certificate present** (if not, refer to [Cloudmos instructions](https://github.com/DecloudNodesLab/Guides/blob/main/English/Cloudmos.md#account-connection-and-preparation-for-work)). Next, press the `DEPLOY` button, select the empty `Empty` template and copy the contents of [deploy.yml](https://raw.githubusercontent.com/DecloudNodesLab/Kadena/main/deploy.yml).
___

<p align="center"><img src="https://user-images.githubusercontent.com/23629420/223087667-86967145-5557-49ad-ba2c-449d51f284c4.gif" width=70% </p>

___
The `Kadena` node requires a **dedicated IP address and static external ports**, for this you need to make small changes to the manifest (deploy.yml),
namely, replace `your_endpoint_name` in the `endpoints` and `expose` sections with a unique name (**Latin lowercase characters only!**)

* `--p2p-hostname=` - leave blank for first deployment.

<p align="center"><img src="https://user-images.githubusercontent.com/23629420/223088770-40ea05f4-7b2e-45ff-b603-c6a6644e4e2a.gif" width=70% </p>

We don't know what **IPv4** address we'll be assigned before starting the deployment, so we'll start the deployment with an empty `--p2p-hostname`. We will fill it in as soon as we get the **IPv4** address from the provider and update our deployment. <br/>
It's time to ask for current offerings in the computing power market. We press `CREATE DEPLOYMENT`, confirm the transaction (**5 AKT** will be frozen) and wait for offers from providers.
  
<br/>
  
<p align="center"><img src="https://user-images.githubusercontent.com/23629420/223093591-ee9a601b-95c6-491e-99e0-1b6bfc92bc6f.gif" width=70% </p>

<br/>
  
The number of providers that are willing to provide computing power **with the static IP function** is currently limited, so it is possible that no provider will respond to your offer. So, I chose an available one and continued to fork.<br/>
In the logs, we can see the **IPv4** address assigned to us. It also appears on the `LEASES` tab of our deployment.
All we have to do is copy it, paste it into our manifest (deploy.yml) on the `UPDATE` page and update the deployment. <br/>
Pay attention to the correct filling, the data must be INSIDE the quotes, for example: <br/> `'--p2p-hostname=YOUR_STATIC_IP_ADDRESS'` <br/>
Here's what it looks like:

<p align="center"><img src="https://user-images.githubusercontent.com/23629420/223095613-d7c83ce2-583f-48fa-a8d9-9f8a19996e1f.gif" width=70% </p>

Example of correct working logs:<br/>

  <p align="center"><img src="https://user-images.githubusercontent.com/23629420/223098180-830373ff-a316-43cd-af6b-8afcab5e12ae.png" width=70% </p>

In the browser, by going to the address `https://<public-ip>:1789/chainweb/0.0/mainnet01/cut` you can observe the operation of the node via the web socket. <br/>

<p align="center"><img src="https://user-images.githubusercontent.com/23629420/223097335-f5421224-fbc4-4b92-8563-8741054bee13.png" width=70% </p>

This completes the installation!<br/> <br/>
Thank you for using **Akash Network**!
