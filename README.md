# Laboratory work №1
Lesson 1, 2, 3
Хамидулина Камилла ПРО-227
Creating a window, a point and a triangle in OpenGL freeglut.

# glutInit(&argc, argv)
GLUT initialization. The first parameter is a pointer to the number of arguments in the command line, and the second is a pointer to an array of arguments.

# glutInitDisplayMode(GLUT_DOUBLE | GLUT_RGBA)
Sets the display mode for the window:
  
•	GLUT_DOUBLE Output to the window is carried out using 2 buffers. Rendering happens to the background buffer while another buffer is being displayed. Used for animation to eliminate the flickering effect.
  
•	GLUT_RGBA A color buffer. Three-channel RGB color model, supplemented with a fourth alpha channel that sets the transparency of the color. The value 0 corresponds to full transparency, 1 - opacity.

# glutInitWindowSize(1024, 768);
Sets the window size

# glutInitWindowPosition(100, 100);
Sets the window position

# glutCreateWindow("Tutorial 01");
Creates a window with the given title

# glutDisplayFunc(RenderSceneCB);
Since glut takes control of the Windows system, most of the program's actions are done through callbacks. We pass a callback to this function, which will be called by Glut to render 1 frame

# glClearColor(0, 0, 0, 0);
