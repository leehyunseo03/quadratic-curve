# quadratic-curve
이차곡선 (포물선, 타원, 쌍곡선)을 그리는 코드입니다



import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(-10, 10, 100)
y = np.linspace(-10, 10, 100)

a, b = np.meshgrid(x,y)
 
r,o,h = input().split()

r = int(r)
o = int(o)
h = int(h)

p = b**2 - r*a - o*b - h     #parabola : 포물선의 방정식
e = (a**2)/r + (b**2)/o - h  #ellipse : 타원의 방정식
h = (a**2)/r - (b**2)/o - h  #hyperbolic : 쌍곡선의 방정식

figure, axes = plt.subplots()

axes.contour(a,b,p,[0],colors='r')
axes.contour(a,b,e,[0],colors='b')
axes.contour(a,b,h,[0],colors='g')

axes.set_aspect(1)
plt.grid()
plt.show()
