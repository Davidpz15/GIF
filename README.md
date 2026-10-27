
from PIL import Image, ImageDraw

frames = []

for x in range(0, 200, 10):
    img = Image.new("RGB", (250, 100), "white")
    dibujo = ImageDraw.Draw(img)
    dibujo.ellipse((x, 30, x + 40, 70), fill="red")
    frames.append(img)

frames[0].save("animacion.gif", save_all=True, append_images=frames[1:], duration=100, loop=0)
