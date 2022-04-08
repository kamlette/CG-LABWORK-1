# Laboratory work №1
Lesson 1, 2, 3
Хамидулина Камилла ПРО-227
Creating a window, a point and a triangle in OpenGL freeglut.
____
## Lesson 1. Creating a window.
### glutInit(&argc, argv)
GLUT initialization. The first parameter is a pointer to the number of arguments in the command line, and the second is a pointer to an array of arguments.

### glutInitDisplayMode(GLUT_DOUBLE | GLUT_RGBA)
Sets the display mode for the window:
  
•	GLUT_DOUBLE Output to the window is carried out using 2 buffers. Rendering happens to the background buffer while another buffer is being displayed. Used for animation to eliminate the flickering effect.
  
•	GLUT_RGBA A color buffer. Three-channel RGB color model, supplemented with a fourth alpha channel that sets the transparency of the color. The value 0 corresponds to full transparency, 1 - opacity.

### glutInitWindowSize(1024, 768);
Sets the window size

### glutInitWindowPosition(100, 100);
Sets the window position

### glutCreateWindow("Tutorial 01");
Creates a window with the given title

### glutDisplayFunc(RenderSceneCB);
Since glut takes control of the Windows system, most of the program's actions are done through callbacks. We pass a callback to this function, which will be called by Glut to render 1 frame

### void glClearColor(GLfloat red, GLfloat green, GLfloat blue, GLfloat alpha)
Specifies the red, green, blue, and alpha values used by glClear to clear the color buffers. Values specified by glClearColor are clamped to the range [0,1].

### glClear(GL_COLOR_BUFFER_BIT);
Clear buffer.

### glutSwapBuffers();
We are changing the buffer we were drawing to the buffer we are displaying on the screen.
____
## Lesson 2. Creating a point.

### GLenum res = glewInit();
Initialize the Glew library, which provides efficient runtime mechanisms for determining which OpenGL extensions are supported on the target platform.
### if (res != GLEW_OK) { fprintf(stderr, "Error: '%s'\n", glewGetErrorString(res)); return 1; }
Checking if it was intitialized without errors.
### glEnableVertexAttribArray(GLuint index) | glDisableVertexAttribArray(GLuint index)
Enable or disable a generic vertex attribute array specified by index. If enabled, the values in the generic vertex attribute array will be accessed and used for rendering when calls are made to vertex array commands such as glDrawArrays, glDrawElements, glDrawRangeElements, glMultiDrawElements, or glMultiDrawArrays.
### glBindBuffer(GL_ARRAY_BUFFER, VBO);
Specify that buffer will be storing an array of vertices.
### void glVertexAttribPointer(GLuint index, GLint size, GLenum type, GLboolean normalized, GLsizei stride, const GLvoid * pointer)
Index specifies the index of the generic vertex attribute to be modified. 
Size specifies the number of components per generic vertex attribute. (1, 2, 3 or 4). 
Type specifies the data type of each component in the array (for example GL_BYTE, GL_INT).
Normalized specifies whether fixed-point data values should be normalized (GL_TRUE) or converted directly as fixed-point values (GL_FALSE) when they are accessed.
Stride specifies the byte offset between consecutive generic vertex attributes. If 0, the generic vertex attributes are understood to be tightly packed in the array. The initial value is 0.
Pointer specifies a offset of the first component of the first generic vertex attribute in the array in the data store of the buffer currently bound to the GL_ARRAY_BUFFER target. The initial value is 0.
### 
