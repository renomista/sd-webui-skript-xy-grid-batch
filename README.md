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
