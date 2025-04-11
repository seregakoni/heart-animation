# heart-animation
import numpy as np
import matplotlib.pyplot as plt
import matplotlib.animation as animation

def heart_shape(t):
    x = 0.5 * np.sin(t) ** 3
    y = 0.5 * (0.8125 * np.cos(t) - 0.3125 * np.cos(2*t) - 0.125 * np.cos(3*t) - 0.0625 * np.cos(4*t))
    return x, y

def update(frame, line):
    t = np.linspace(0, frame * np.pi / 50, 100)
    x, y = heart_shape(t)
    line.set_data(x, y)
    return line,

def animate_heart():
    fig, ax = plt.subplots()
    ax.set_xlim(-0.6, 0.6)
    ax.set_ylim(-0.6, 0.6)
    ax.set_xticks([])
    ax.set_yticks([])
    ax.set_title("💖 Animated Heart")
    
    t = np.linspace(0, 2 * np.pi, 100)
    x, y = heart_shape(t)
    line, = ax.plot([], [], "r", linewidth=3)
    
    ani = animation.FuncAnimation(fig, update, frames=100, fargs=(line,), interval=50, blit=True)
    plt.show()

# Run the animation
animate_heart()
ыфвыуцк
