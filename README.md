# EXP 1 : Linear and Circular Convolution

## AIM: 

 To perform Linear and Circular Convolution for two given sequence using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (Linear Convolution): 
```
clc;
clear;
close;

x = input("Enter x(n) as a vector, e.g., [1 2 0 2]: ");
h = input("Enter h(n) as a vector, e.g., [0 1]: ");
y = conv(x, h);
disp(y, "Linear Convolution y(n) = ")
subplot(3,1,1);
plot2d3(0:length(x)-1, x);
title("x(n)");
xlabel("n");
ylabel("Amplitude");

subplot(3,1,2);
plot2d3(0:length(h)-1, h);
title("h(n)");
xlabel("n");
ylabel("Amplitude");

subplot(3,1,3);
plot2d3(0:length(y)-1, y);
title("y(n) = x(n) * h(n)");
xlabel("n");
ylabel("Amplitude");
```

## PROGRAM (Circular Convolution): 
```
clc;
clear;
close;

x = input("Enter x(n) as a vector, e.g., [1 2 3 4]: ");
h = input("Enter h(n) as a vector, e.g., [1 2 3 4]: ");

N = length(x);
if length(h) < N then
    h = [h, zeros(1, N - length(h))];
elseif length(h) > N then
    x = [x, zeros(1, length(h) - N)];
    N = length(h);
end
X = fft(x, -1);   
H = fft(h, -1);
Y = X .* H;
y = fft(Y, 1);    
disp(real(y), "Circular Convolution y(n) = ");
subplot(3,1,1);
plot2d3(0:N-1, x);
title("Input Sequence x[n]");
xlabel("n");
ylabel("Amplitude");

subplot(3,1,2);
plot2d3(0:N-1, h);
title("Input Sequence h[n]");
xlabel("n");
ylabel("Amplitude");

subplot(3,1,3);
plot2d3(0:N-1, real(y));
title("Circular Convolution y[n]");
xlabel("n");
ylabel("Amplitude");
```

## OUTPUT (Linear Convolution): 

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/a7aceda1-f7ff-4a0a-a4e4-b0ca7ac5eb99" />

## OUTPUT (Circular Convolution): 

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/861d3d24-c0fa-4a25-ab94-cd86cde233f3" />

## RESULT: 

Thus, the linear convolution and circular convolution of the two given sequences were performed and its result was verified.
