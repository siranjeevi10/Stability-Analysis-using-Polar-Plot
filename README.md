# Stability-Analysis-using-Polar-Plot

## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 

## Apparatus Required:
Computer with MATLAB software

## Theory:
![WhatsApp Image 2025-11-27 at 18 37 25_076ee6f0](https://github.com/user-attachments/assets/e266a92b-6780-4ce4-af6e-4c6c8bb388a2)
![WhatsApp Image 2025-11-27 at 18 37 24_b25c1e50](https://github.com/user-attachments/assets/be552fa2-4068-40d2-8594-8b125ecaccf0)
![WhatsApp Image 2025-11-27 at 18 37 24_20cef8af](https://github.com/user-attachments/assets/acd176cf-a3e9-43db-acef-c68398b55038)



## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 

```
num=[10]
den=[0.1 0.7 1 0]
sys=tf(num,den)
[mag,phase,W]=bode(sys)
mag=squeeze(mag)
phase=squeeze(phase)
phase1=deg2rad(phase)
polarplot(phase1,mag,'linewidth',1.5)
grid on
[Gm Pm Wpc Wgc]=margin(sys)
if(Wpc>Wgc)
    disp('stable')
elseif(Wpc == Wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```

## Output:

<img width="713" height="640" alt="image" src="https://github.com/user-attachments/assets/4711b265-6492-408c-8d8f-c70d45e66a71" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.7 <br>
Phase Margin = -8.8865 <br>
Gain crossover frequency = 3.7565 <br>
Phase crossover frequency = 3.1623 <br>
The system is unstable.
