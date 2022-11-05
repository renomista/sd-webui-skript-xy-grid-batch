# sd-webui-skript-xy-grid-batch
Adapted Version of the xy_grid script by AUTOMATIC1111 added Batch Processing Feature


Use like the standard XY grid Script

![image](https://user-images.githubusercontent.com/117518688/200119466-8ac069d5-313f-4f37-9e46-7482b982c183.png)

If you check the "Batch Process" Feature the script will instead bead the file batch.json from the main dir of the SD-WebUI (where also the bat/sh files are located.
This file needs to contain a valid json with a list/array of dictonaries/objects.
For each List/Array entry one Grid is created using the original settings from the ui but replacing them with values from the bictionary/object if present
Currently supported replaceable Values are:

xvalues: the value field of the X Axis of the Grid
yvalues: the value field of the Y Axis of the Grid
seed: The Seed number
prompt: the Prompt string
negative_prompt: the negative prompt String

Example for such a Json:
[
	{"xvalues":"8-13","yvalues":"20,35,65"},
	{"xvalues":"8-13"},
	{"yvalues":"20,35,65"},
	{"xvalues":"8-3","yvalues":"20,35,65", "prompt":"beautiful young woman, smiling, wearing a colorful sundress, full body shot"},
	{"seed":2368520650,"xvalues":"8-13","yvalues":"20,35,65"},
	{"seed":2368920650,"yvalues":"20,35,65","negative_prompt":"european, blond"},
	{"xvalues":"8-13","yvalues":"20,35,65","prompt":"beautiful older woman, smiling, wearing a black and white etui dress, full body shot","negative_prompt":"short hair, european"}
]

Examples Results:

Entry {"xvalues":"8-13","yvalues":"20,35,65"}:
![xy_grid-0173-1740045880-beautiful young woman, smiling, wearing a colorful sundress](https://user-images.githubusercontent.com/117518688/200120290-a6238f0b-9c83-413d-bcc3-ba32b8ec573d.jpg)

Entry {"xvalues":"8-13"}:
![xy_grid-0174-1740045880-beautiful young woman, smiling, wearing a colorful sundress](https://user-images.githubusercontent.com/117518688/200120303-ec52f8df-75ed-4856-83f3-d8d4dbb55940.png)

Entry {"yvalues":"20,35,65"}:
![xy_grid-0175-1740045880-beautiful young woman, smiling, wearing a colorful sundress](https://user-images.githubusercontent.com/117518688/200120307-d2c7553c-e9f3-458f-8502-df196dfe902b.png)

Entry {"xvalues":"8-3","yvalues":"20,35,65", "prompt":"beautiful young woman, smiling, wearing a colorful sundress, full body shot"}:
![xy_grid-0176-1740045880-beautiful young woman, smiling, wearing a colorful sundress, full body shot](https://user-images.githubusercontent.com/117518688/200120328-d442dec4-fecc-4791-bedd-cb8efa7f694a.jpg)


Entry {"seed":2368520650,"xvalues":"8-13","yvalues":"20,35,65"}:
![xy_grid-0177-2368520650-beautiful young woman, smiling, wearing a colorful sundress](https://user-images.githubusercontent.com/117518688/200120353-ec595a08-46f6-46b9-bb65-15ccadc3c405.jpg)


Entry {"seed":2368920650,"yvalues":"20,35,65","negative_prompt":"european, blond"}:
![xy_grid-0178-2368920650-beautiful young woman, smiling, wearing a colorful sundress](https://user-images.githubusercontent.com/117518688/200120375-e5a15965-9128-4c37-8fe1-71ced7dd8ab6.png)


Entry {"xvalues":"8-13","yvalues":"20,35,65","prompt":"beautiful older woman, smiling, wearing a black and white etui dress, full body shot","negative_prompt":"short hair, european"}:
![xy_grid-0179-1740045880-beautiful older woman, smiling, wearing a black and white etui dress, full body shot](https://user-images.githubusercontent.com/117518688/200120587-4fe7d93b-3049-4a64-82bb-862b5db37419.jpg)


(All Examples created using Zeipher's F222 Model)
