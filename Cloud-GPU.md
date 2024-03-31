# Guide: Rent a Cloud GPU

This is a step-by-step guide on how to run the Stable Diffusion server remotely on cloud services like [runpod.io](https://www.runpod.io) or [vast.ai](https://vast.ai). This allows you to use the plugin without installing a server on your local machine, and is a great option if you don't own a powerful GPU. There is no subscription, you typically pay between 0.25$ to 0.50$ per hour.

## runpod.io

[runpod.io](https://www.runpod.io) is fairly stream-lined, but offers limited information about download speeds, and is a bit more pricey.

### Step 1: Sign up and add funds

Go to [runpod.io](https://www.runpod.io) and create an account. Go to "Billing" and add funds (one-time payment, minimum 10$, card required).

### Step 2: Select a GPU

I choose community cloud and select 1x RTX 3080. It's cheap and fast! Click _Deploy_.

![runpod-1](https://github.com/Acly/krita-ai-diffusion/assets/6485914/e58e5121-bd38-473d-8b66-14efcc9a4405)

You are free to choose one of the other options of course.

### Step 3: Select the template

Runpod supports all kinds of workloads. To run a server for the Krita plugin, select "Stable Diffusion ComfyUI for Krita". Just typing "krita" into the search bar should find it, or use [this link](https://runpod.io/gsc?template=8myumeqonw&ref=of4awcqw). Click _Continue_.

![runpod-2](https://github.com/Acly/krita-ai-diffusion/assets/6485914/7d0bcda6-448d-4ae7-bfbf-c363dff976c1)


### Step 4: Deploy!

You will get a cost summary. Click _Deploy_.

Now you have to wait until the server is up. This can take a while (~10 minutes) depending on the download speed of your pod. Eventually it should look like this:

![runpod-3](https://github.com/Acly/krita-ai-diffusion/assets/6485914/a4396f76-9bea-4a36-abf3-4b4785fd9326)

### Step 5: Connect

Once your pod is running, click _Connect_ and choose "HTTP Service [Port 3001]".

![runpod-4](https://github.com/Acly/krita-ai-diffusion/assets/6485914/4866179d-2b14-4b36-8d04-602a3844891f)

This should open ComfyUI running in your browser. Now simply copy the URL into the Krita plugin and connect!

![runpod-5](https://github.com/Acly/krita-ai-diffusion/assets/6485914/b925b78d-81b8-43e8-9283-191fd8f1da59)

![runpod-6](https://github.com/Acly/krita-ai-diffusion/assets/6485914/fc24c3fd-51af-4eec-904f-25f6b19c7453)

### Afterwards

After you're done using the pod, remember to stop it. You can keep it inactive to potentially reuse it later, but it's not free. To avoid charges, make sure to discard/delete the pod.



## vast.ai

[vast.ai](https://vast.ai) has a very similar offering. You get more details about the machine you will run on, but it also requires you to filter the available pods to get what you want. Minimum initial funds is 5$.

The UI is very similar to runpod.io and so are the steps to set it up.

### Template

You can use [this template](https://cloud.vast.ai/?ref_id=87451&creator_id=87451&name=Stable%20Diffusion%20ComfyUI%20for%20Krita). Try to select a pod in your region with good internet connection. Click _Rent_.

![vast-1](https://github.com/Acly/krita-ai-diffusion/assets/6485914/4648830d-e779-43ba-b0f7-118855ffa8bf)

### Connecting

Once your instance has finished loading and is running, click the button which displays the port range to find the URL to connect.

![vast-2](https://github.com/Acly/krita-ai-diffusion/assets/6485914/81a1e6ba-fc30-4340-bccc-45319644252a)

The URL will be the one which maps to port 3001. Copy it into Krita and connect. _Make sure it doesn't contain any spaces!_

![vast-3](https://github.com/Acly/krita-ai-diffusion/assets/6485914/a9c62bbf-6907-4030-a6cf-8a0c48b0b435)

![vast-4](https://github.com/Acly/krita-ai-diffusion/assets/6485914/389c3c23-f2ac-4ed8-804f-d98e79ad6401)


## sailflow.ai

[sailflow.ai](https://www.sailflowai.com) is a GPU cloud platform, which allows you to start krita-ai-diffusion faster. You don't have to install ComfyUI in the cloud GPU server in advance, you just follow the instruction below, create a job, connect to the web address and then done.

### Step 1: Sign up

Go to [sailflow.ai](https://www.sailflowai.com) and create an account, try referral code: R5QXRVE6.

<img width="1440" alt="截圖 2024-03-29 上午11 26 31" src="https://github.com/x1y2z3456/krita-ai-diffusion/assets/33689381/034c24b4-ae46-403c-a995-6f749df1253e">

### Step 2: Select the template

You can select Krita template immediately at Home page. Feel free to start, being comfortable to top-up later or try subscription plans. Click _Krita_.

<img width="1440" alt="截圖 2024-03-29 上午10 53 32" src="https://github.com/x1y2z3456/krita-ai-diffusion/assets/33689381/6ab6176c-80ff-4e65-a6b2-57d925b14c32">

You are free to choose one of the other options of course.

### Step 3: Deploy!

You will get a cost summary. Click _Submit_.

<img width="1440" alt="截圖 2024-03-29 上午11 39 19" src="https://github.com/x1y2z3456/krita-ai-diffusion/assets/33689381/3e26729f-6f15-439c-806f-4cb8ae5e3a04">

Now you have to wait until the server is up. This will be available soon (~1 minutes) depending on the download speed of your pod. Eventually it should look like this:

### Step 4: Connect

Once your pod is running, you may notice that _SD APP_ button has been enabled and you can connect to ComfyUI through this button.

<img width="1440" alt="截圖 2024-03-29 下午12 02 53" src="https://github.com/x1y2z3456/krita-ai-diffusion/assets/33689381/74194475-4411-4549-8c36-07f87ecf0953">

This should open ComfyUI running in your browser. Now simply copy the URL into the Krita plugin and connect!

<img width="1440" alt="截圖 2024-03-29 下午12 42 24" src="https://github.com/x1y2z3456/krita-ai-diffusion/assets/33689381/8aee6193-25d4-467b-8cdf-1588b3e97612">

![sailflowai-6](https://github.com/x1y2z3456/krita-ai-diffusion/assets/33689381/a26c7699-fb17-4245-8b8b-3fa95fd2116b)

### Afterwards

After you're done using the pod, remember to stop it. You can keep it inactive to potentially reuse it later, but it's not free. To avoid charges, make sure to discard/delete the pod.




## Custom checkpoints and LoRA

If you want to use custom models you will have to download them to the pod. There is no UI for this yet, but it can be done via SSH terminal.

Either use the web terminal, or connect via ssh.
* Download Checkpoints to `/models/checkpoints`
* Download LoRA to `/models/lora`

```
cd /models/checkpoints
wget --content-disposition 'http://file-you-want-to-download'
```

After download is complete, click the refresh button in Krita and they should show up.

![cloud-gpu-custom-checkpoint](https://github.com/Acly/krita-ai-diffusion/assets/6485914/c7b2a9ad-4995-42f6-9f09-e8b69a518b2a)

