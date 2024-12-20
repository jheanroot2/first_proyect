# first_proyect
# This is a code to create a Christmas tree in Python.
import matplotlib.pyplot as plt 
from mpl_toolkits.mplot3d import Axes3D
import numpy as np

#figura eje 3D
fig = plt.figure()
ax = fig.add_subplot(111, projection = '3d')

#parametros del arbol
num_layers = 10
points_per_layer = 100

#agregar estrella
ax.scatter(0, 0, 11, c="gold", marker='*', s=400, label='Feliz Navidad')

#genera la capa del arbol
for layer in range(num_layers):
    z = np.full(points_per_layer,layer)
    r= (num_layers - layer) / 2
    theta = np.linspace(0, 2 * np.pi, points_per_layer)
    x = r * np.cos(theta)
    y = r * np.sin(theta)
    ax.scatter(x, y, z, c='green', s=10)

    num_baubles = 50

# codigo para las bolas de colores
for _ in range(num_baubles):
    z = np.random.uniform(0, num_layers)
    r = (num_layers - z) / 2
    theta = np.random.uniform(0, 2 * np.pi)
    x = r * np.cos(theta)
    y = r * np.sin(theta)
    ax.scatter(x, y, z, c='red', s=20)
for _ in range(num_baubles):
    z = np.random.uniform(0, num_layers)
    r = (num_layers - z) / 2
    theta = np.random.uniform(0, 2 * np.pi)
    x = r * np.cos(theta)
    y = r * np.sin(theta)
    ax.scatter(x, y, z, c='gold', s=20)
for _ in range(num_baubles):
    z = np.random.uniform(0, num_layers)
    r = (num_layers - z) / 2
    theta = np.random.uniform(0, 2 * np.pi)
    x = r * np.cos(theta)
    y = r * np.sin(theta)
    ax.scatter(x, y, z, c='blue', s=20)

    #base del arbol
    z_trunk = np.linspace(-2, 0, 10)
    x_trunk = np.zeros_like(z_trunk)
    y_trunk = np.zeros_like(z_trunk)
    ax.plot(x_trunk, y_trunk, z_trunk, c='brown', linewidth=5)

        #etiqueta de los ejes
    ax.set_xlabel('Eje X (FELIZ)')
    ax.set_ylabel('Eje Y (NAVIDAD)')
    ax.set_zlabel('Eje Z (A TODOS)')
    
        #mostrar el grafico
plt.show()
