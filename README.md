# FIR-FILTER-DESIGN
# EXP 4 c: Design-of-FIR-Digital-Filter-using-Hanning-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Hanning-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
~~~
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = Wc/ %pi ; 
else 
hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));  
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are')  
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of  FIR LPF using Hanning Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR LPF using Hanning Window'); 
~~~

# CALCULATION:
<img width="1205" height="748" alt="image" src="https://github.com/user-attachments/assets/ac16a966-04e7-4a43-ae08-6ef64a11e555" />
<img width="1186" height="1015" alt="image" src="https://github.com/user-attachments/assets/3c90ad1c-5a40-4ee5-a249-22571bdac615" />

# OUTPUT: 
<img width="511" height="438" alt="image" src="https://github.com/user-attachments/assets/2bb56fa1-615e-4779-9f38-34032c89d6e6" />
<img width="762" height="719" alt="image" src="https://github.com/user-attachments/assets/91180633-959d-43e5-a3aa-b9fcba00b318" />


# RESULT: 

Thus design of low pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
~~~
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = 1-Wc/ %pi ; 
else 
hd(n) = -sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR HPF using Hanning Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR HPF using Hanning Window'); 
~~~

# CALCULATION:
<img width="871" height="1280" alt="image" src="https://github.com/user-attachments/assets/d5460e5b-548b-413e-b42d-19643ae61d31" />

# OUTPUT: 
<img width="495" height="485" alt="image" src="https://github.com/user-attachments/assets/c5937117-1e21-4b7f-b145-d2e576a0f949" />
<img width="758" height="730" alt="image" src="https://github.com/user-attachments/assets/93189d49-debe-4e24-a940-e1b5a44f433c" />


# RESULT: 
Thus design of HIGH pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
~~~
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =(Wc2-Wc1)/%pi ; 
else 
hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
//Hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Hanning Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Hanning Window'); 
~~~

# CALCULATION:
<img width="1284" height="1103" alt="image" src="https://github.com/user-attachments/assets/c880a8f5-0d6b-4c96-ab92-54ca69ad8990" />

# OUTPUT: 
<img width="591" height="463" alt="image" src="https://github.com/user-attachments/assets/a2fbc95d-40e5-4928-9061-0405b1800fef" />
<img width="757" height="726" alt="image" src="https://github.com/user-attachments/assets/4b80e2df-d17e-4c8d-bf56-b27559237dc9" />


# RESULT: 
Thus design of BAND pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
~~~clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =1-((Wc2-Wc1)/%pi); 
else 
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
//Hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Hanning Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Hanning Window');

~~~

# CALCULATION:
<img width="1600" height="1030" alt="image" src="https://github.com/user-attachments/assets/ae6c6c3b-3c51-4b1e-8e31-758997342c25" />

# OUTPUT: 
<img width="570" height="505" alt="image" src="https://github.com/user-attachments/assets/4b81223e-ba4e-4981-b4d7-7573f5a63036" />
<img width="765" height="728" alt="image" src="https://github.com/user-attachments/assets/803a0e26-6dba-428c-8a53-c9b17b4ab92e" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.
