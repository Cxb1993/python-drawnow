
### `drawnow` for matplotlib

MATLAB(R) has a great feature where it allows you to update a figure. You can
simply call `drawnow` and have your figure update. This is nice if you're
running a simulation and want to see the results every iteration. It'd sure be
nice if Python/matplotlib had a similar feature to update the plot each
iteration.


Usage:
    
    from drawnow import drawnow, drawnow_init

    drawnow_init()
    x = zeros((N,N))

    def function_to_draw_figure():
        figure()
        imshow(x) # python's global scope
        #show()   # don't call show()!

    for i in arange(x):
        x.flat[i] = 1
        drawnow(function_to_draw_figure)
        #show() # only if you want to press <enter> each figure update

If you want the program to wait after each figure update, call `show()` after
`drawnow(function_to_draw_figure)`.

### Installation
1. Download this repository.
2. Put `drawnow.py` in your current folder or the drawnow folder in
   `../python/site-packages/`.
