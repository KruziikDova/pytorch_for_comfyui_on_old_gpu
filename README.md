# pytorch_for_comfyui_on_old_gpu
Trivially easy solution to "PyTorch no longer supports this GPU because it is too old" error for Stable Diffusion ComfyUI windows portable nvidia distribution.

!!! THE SOLUTION WORKS ONLY FOR PRE-RTX GPUs THAT SUPPORT CUDA 6.1 !!!
Such as:
- GeForce GTX 1080 Ti
- GeForce GTX 1080
- GeForce GTX 1070 Ti
- GeForce GTX 1070
- GeForce GTX 1060
- GeForce GTX 1050
- NVIDIA TITAN Xp
- NVIDIA TITAN X

----- THE GUIDE -----

Automatic:
1. Download the edited "update_comfyui_and_python_dependencies.bat" file from the "Releases" tab of this github repository or via URL link: https://github.com/KruziikDova/pytorch_for_comfyui_on_old_gpu/releases/download/Release/update_comfyui_and_python_dependencies.bat
2. Go to your "ComfyUI_windows_portable_nvidia" folder.
3. Open the "update" folder.
4. Overwrite the "update_comfyui_and_python_dependencies.bat" file with the one you have downloaded in step 1 of this guide.
5. Run the "update_comfyui_and_python_dependencies.bat" file.
6. Press "enter" or "space" when the command prompt window asks you to "press any key".
7. Wait for Pytorch to reinstall in "python_embeded" folder.
8. Done, you can now use your ComfyUI to your heart's content.

Manual:
1. Go to your "ComfyUI_windows_portable_nvidia" folder.
2. Open the "update" folder.
3. Right-click on the "update_comfyui_and_python_dependencies.bat" file.
4. Press "edit" or choose to edit it with your favorite notepad software.
5. Look for this line:
   "..\python_embeded\python.exe -s -m pip install --upgrade torch torchvision torchaudio  --extra-index-url https://download.pytorch.org/whl/cu129 -r ../ComfyUI/requirements.txt pygit2"
6. Change "upgrade" to "force-reinstall".
7. Change "cu129" to "cu126".
8. The line should look like this:
   "..\python_embeded\python.exe -s -m pip install --force-reinstall torch torchvision torchaudio  --extra-index-url https://download.pytorch.org/whl/cu126 -r ../ComfyUI/requirements.txt pygit2"
9. Save the file and exit your notepad software that you used to edit the file now.
10. Run the "update_comfyui_and_python_dependencies.bat" file.
11. Press "enter" or "space" when the command prompt window asks you to "press any key".
12. Wait for Pytorch to reinstall in "python_embeded" folder.
13. Done, you can now use your ComfyUI to your heart's content.

Potential issues:
1. If you don't have the "update" folder and/or the "update_comfyui_and_python_dependencies.bat", you should redownload ComfyUI_windows_portable_nvidia from the official website: https://github.com/comfyanonymous/ComfyUI/releases .
2. If the ComfyUI's command prompt window gives you the "Torch not compiled with CUDA enabled" error, you might want to download CUDA Toolkit from here: https://developer.nvidia.com/cuda-downloads . Then you should install it, run it and compile the "torch", "torchvision" and "torchaudio" packages with CUDA 6.1 enabled.
