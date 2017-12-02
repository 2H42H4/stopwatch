# stopwatch
python stopwatch
# template for "Stopwatch: The Game"
import simplegui

# define global variables
count = 0

# define helper function format that converts time
# in tenths of seconds into formatted string A:BC.D
def format(t):
    global count
    count = t
    if count < 10:
        return "0:00." + str(count)
    elif count >= 10 and count < 100:
        return "0:0" + str(count // 10) + "." + str(count % 10)
    elif count >= 100
    
    
    else:
        return ":)"
    
# define event handlers for buttons; "Start", "Stop", "Reset"
def start():
    timer.start()
def stop():
    timer.stop()
def reset():
    global count
    timer.stop()
    count = 0

# define event handler for timer with 0.1 sec interval
def tick():
    global count 
    count += 1
    
# define draw handler
def draw(canvas):
    canvas.draw_text(str(format(count)), [100, 120], 50, "white") 
    
# create frame 
frame = simplegui.create_frame("Timer game", 400, 200)
frame.add_button("Start", start, 50)
frame.add_button("Stop", stop, 50)
frame.add_button("Reset", reset, 50)

# register event handlers
timer = simplegui.create_timer(100, tick)
frame.set_draw_handler(draw)

# start frame
frame.start()

# Please remember to review the grading rubric
