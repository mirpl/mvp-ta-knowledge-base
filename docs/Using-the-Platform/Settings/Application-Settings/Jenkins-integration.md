# Jenkins integration



## ***Pluggin upload***

To integrate Jenkins with the platform, you need to add a plugging first.

To do so, click the 'Manage Jenkins'(**1**), and, then, the 'Manage Pluggins'(**2**) option.

![plug](https://github.com/mirpl/mvp-ta-knowledge-base/blob/master/assets/imeges8/image3.png?raw=true)


There, click the 'Advanced' tab.

![adv](https://github.com/mirpl/mvp-ta-knowledge-base/blob/master/assets/imeges8/image2.png?raw=true)

Scroll to the 'Upload Pluggin', and choose a respective file.

![apl](https://github.com/mirpl/mvp-ta-knowledge-base/blob/master/assets/imeges8/image1.png?raw=true)

## ***Freestyle Powerfarm Plugin usage***

Go to your projects, and click the 'Freestyle Powerfarm Plugin usage'. Next, choose 'Configuration' option, and scroll down to the 'Building' section. 

You need to set up two steps:

1. Create Job
2. Get Job Status

### Create Job

Provide following data:

- **Workflow ID** - Enter in Workflow and copy ID from URL. e.g. for workflow https://powerfarm.ai/mir-mvp/workflows/details/-MJaLOz8B4R8ANSGIwOh you should use -MJaLOz8B4R8ANSGIwOh as jobID.
- **Created by** - displayed as creator of job in Powerfarm platform.
- **Token** - generate new [Access Token](https://docs.powerfarm.ai/docs/mvp-ta-knowledge-base/docs/Using-the-Platform/Settings/Access-Token.md) at Settings in the platform.
- **Job configuration JSON** - you can check it at [API documentation](https://docs.powerfarm.ai/docs/mvp-ta-knowledge-base/PF-API.v1.json/paths/~1jobs/post)

### Get Job Status

Provide following data:

- **Job ID** - Enter jobID which you want read. You can use ${PF_JOB_ID} as value to use last job created in Jenkins.
- **Token** - generate new [Access Token](https://docs.powerfarm.ai/docs/mvp-ta-knowledge-base/docs/Using-the-Platform/Settings/Access-Token.md) at Settings in the platform.

## ***Powerfarm Pipeline*** 

Go to your projects, and click the 'Powerfarm Pipeline'. Next, choose 'Configuration' option, and scroll down to the 'Pipeline' section to provide respective pipeline script. 