<div align="center">
  <img src="https://user-images.githubusercontent.com/83492589/231606495-83f38148-e78f-4ea4-a35b-dd2fc8863d82.png" width="500" height="300" />
  
  
  
  # Stablediffy 

  *A vicuna based prompt engineering tool for stable diffusion*
  
  **generate awesome images without prompt knowledge**
  
  
  
  <a href="#examples">Examples</a> - <a href="#installation">Installation</a> - <a href="#usage">Usage</a>

  
</div>

## How it works
The Stablediffy.txt file is a prompt-file for the vicuna model, similar to the chat-with-bob.txt file.<br>
First, The situation is described.
Secondly, a few keywords like "dramatic lightning" are listed, to teach vicuna them.
Third, a few sample responses from Stablediffy to the rough sentences from the Human are listed, to teach vicuna how it should respond.
## Examples
<img src="https://user-images.githubusercontent.com/83492589/231573450-efc41738-9d7b-47d2-baee-8483984a25a7.png" width="550" height="550" /> 
Model: Deliberate - 768x768 - Sampling Steps: 20 - Sampling Method: Euler a

#### Request
```
### Human:suggest a prompt for an mysterious house
### Assistant: Mysterious house, haunted mansion, spooky, intricate, sharp details, octane render, unreal engine, photograph, realistic skin texture, photorealistic, hyper realism, highly detailed, 85mm portrait photography, award winning, hard rim lighting photography, dramatic lighting, cinematic lighting, gritty atmosphere, urban, noir style, night scene"
```

## Installation
To install Vicuna, follow the instructions on this repo: https://github.com/vicuna-tools/vicuna-installation-guide/

Once that's done, navigate to the `llama.cpp/prompts` folder

Now, download the Stablediffy.txt file with `wget`
```
wget "https://raw.githubusercontent.com/vicuna-tools/Stablediffy.txt/main/Stablediffy.txt"
```
## Usage 
Navigate back to the `llama.cpp` folder
Run the vicuna model with the Stablediffy.txt prompt-file
```
./main -m ./models/ggml-vicuna-13b-4bit-rev1.bin --repeat_penalty 1.0 --color -i -r "### Human:" -f prompts/Stablediffy.txt
```
This should start processing the Stablediffy.txt file
After the last processed conversation example:

`### Assistant: Car in 1950, highly detailed, classic car, 1950's...`

#### You should see the prompt-input `### Human:`, there you can start asking for stable diffusion prompts

![untitled](https://user-images.githubusercontent.com/83492589/231721945-e58890ed-ac13-4872-a2ae-d1d918b2ca00.gif)
