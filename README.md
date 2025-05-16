<p align="center">
  <img src="https://files.catbox.moe/k3n1fy.png" alt="zena. Banner Logo">
<p align="center">

# about.
Zena (or zena.) is a simple Node.js app intended to be deployed on [Cloudflare workers](https://workers.cloudflare.com/). It's meant to work with the [Hyperbeam API](https://docs.hyperbeam.com/home/introduction) to let users create temporary private virtual machines on websites, or other applications.

# deploying.
1. Fork the repo
2. Make changes in to the config in index.js
3. Go to the Cloudflare dashboard, and select `Compute (Workers)`
4. Press `Create`, then `Import a repository` and select the repo you just created
5. If it's not autofilled, set the build command to `npm run build`.
6. Change the name to what you want your workers.dev link to be, and go to Build Variables.
7. Set a build variable with the name `HB_API_KEY` and a value of your Hyperbeam production key. Encrypt the variable.
8. Save and deploy!

# faq.
> How do I use it?

Make a GET request to `/start-vm`, and you'll get a response like this.

```json
{
  "session_id": "52f968cb-6739-4197-83d7-2305fe5d6f54",
  "embed_url": "https://vwdrccwgpv181powg61ggyvy.hyperbeam.com/Uvloy2c5QZeD1yMF_l1vVA?token=c8iw3SmQglOU0ugfLr3dWY2LalSKI_WOGUldEt8knbw",
  "admin_token": "51JOZEEcMp4trCwbpTS3jjQc0lSmeAZpPfxioDqe73U"
}
```

From there, it should be pretty obvious.

If you want to delete a VM, simply make a DELETE request to `/kill-vm/the-id-of-the-vm-you-want-to-kill`.

> Who did you get this idea from?

VAPOR's private VM's, and frogiee1's 'xena.' virtual machine service.

> Did you use their code?

No. Their code is not public yet.
