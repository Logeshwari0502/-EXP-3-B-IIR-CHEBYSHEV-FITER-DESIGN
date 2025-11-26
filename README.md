# EXP 3 : IIR-CHEBYSHEV-FITER-DESIGN
# REG:212223060137
## AIM: 

 To design an IIR Chebyshev filter  using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (LPF): 
```
clear;
Fs = 5000;         
fc = 1500;         

b = [0.0929 0.2787 0.2787 0.0929];   
a = [1.0000 -0.5772 0.4218 -0.0561];  

Npoints = 512;
[H, f_norm] = frmag(b, a, Npoints);

f = f_norm * Fs;

clf();
plot(f, 20*log10(H + %eps));
xlabel("Frequency (Hz)");
ylabel("Magnitude (dB)");
title("Chebyshev Type I Low Pass Filter (Order 3)");
xgrid();

disp(b, "Numerator coefficients (b):");
disp(a, "Denominator coefficients (a):");

```



## PROGRAM (HPF): 
```
clear;
Fs = 5000;          

fc = 1500;          

b = [0.4218 -0.5772 0.2787 -0.0929];   
a = [1.0000 -0.5772 0.4218 -0.0561];  

Npoints = 512;
[H, f_norm] = frmag(b, a, Npoints);

f = f_norm * Fs;

clf();
plot(f, 20*log10(H + %eps));
xlabel("Frequency (Hz)");
ylabel("Magnitude (dB)");
title("Chebyshev Type I High Pass Filter (Order 3)");
xgrid();

disp(b, "Numerator coefficients (b):");
disp(a, "Denominator coefficients (a):");
```



## OUTPUT (LPF) : 

<img width="1052" height="617" alt="image" src="https://github.com/user-attachments/assets/846df229-f2d4-423a-9896-b0d030bb5fa9" />


## OUTPUT (HPF) : 

<img width="1010" height="586" alt="image" src="https://github.com/user-attachments/assets/8897222f-a2d2-469a-9d09-73622986a47d" />



## RESULT: 

A 3rd-order Chebyshev Type I high-pass filter was designed with cutoff frequency 1500 Hz and sampling frequency 5000 Hz. The frequency response shows ripple in the passband and sharp attenuation in the stopband.
