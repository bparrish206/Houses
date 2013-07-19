Houses
======
import Gui3

canvas_width = 400
canvas_height = 300

def main():
    win = Gui3.Gui()
    win.title('My Scene')
    canvas = win.ca(canvas_width, canvas_height)
    canvas.rectangle([ [-canvas_width/2+2, -canvas_height/2], [canvas_width/2, canvas_height/2-2] ], fill='#00ccff')
    canvas.rectangle([ [-canvas_width/2+2, -canvas_height/2], [canvas_width/2, 0] ], fill='#009900')
    canvas.rectangle([[-90, -100], [10, -50]], fill='blue')
    canvas.rectangle([[-52, -100], [-28, -60]], fill='#996633')
    house(-180, -60, canvas, '#ff7788')
    upTriangle(-100, -50, 120, 30, '#993300', canvas)
    house(-100, -100, canvas)
    tree(60, -60, canvas, '#22cc33')
    house(70, -130, canvas, 'gold')
    tree(100, -40, canvas, '#335500')
    tree(0, -140, canvas, '#aa0000')

    win.mainloop()

def upTriangle(x, y, w, h, color, canvas):
      canvas.polygon([[x, y], [x + w, y], [x + w/2, y + h]],
      fill=color, outline='black')

def ask():
    ask = input('what color do you want your house to be?')
    win = Gui3.Gui()
    win.title('My Scene')
    canvas = win.ca(canvas_width, canvas_height)
    canvas.rectangle([ [-canvas_width/2+2, -canvas_height/2], [canvas_width/2, canvas_height/2-2] ], fill='#00ccff')
    canvas.rectangle([ [-canvas_width/2+2, -canvas_height/2], [canvas_width/2, 0] ], fill='#009900')
    canvas.rectangle([[-90, -100], [10, -50]], fill='blue')
    canvas.rectangle([[-52, -100], [-28, -60]], fill='#996633')
    house(-180, -60, canvas, '#ff7788')
    upTriangle(-100, -50, 120, 30, '#993300', canvas)
    house(-100, -100, canvas)
    tree(60, -60, canvas, '#22cc33')
    house(70, -130, canvas, 'gold')
    house(-50, 0, canvas, ask)
    tree(100, -40, canvas, '#335500')
    tree(0, -140, canvas, '#aa0000')

def house(x, y, canvas, color='blue'):
   canvas.rectangle([[x+10, y], [x+110, y+50]], fill=color)
   canvas.rectangle([[x+48, y], [x+72, y+40]], fill='#996633')
   upTriangle(x, y+50, 120, 30, '#993300', canvas)

def tree(x, y, canvas, color):
    upTriangle(x, y + 25, 50, 100, color, canvas)
    canvas.rectangle([[x+32, y], [x+18, y+24]], fill='brown')    

main()
ask()
