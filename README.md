Download Link: https://assignmentchef.com/product/solved-bme595-homework-01-implement-2d-convolution
<br>
<span style="font-size: 2.61792em; letter-spacing: -1px; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen-Sans, Ubuntu, Cantarell, 'Helvetica Neue', sans-serif;">Background</span>

Convolutions are important. They are the building block of convolutional neural networks. This homework is designed to give you an introduction to the tools used in our course.

<h1>Deliverables</h1>

<ul>

 <li>Two input images of size 1280×720, 1920×1080</li>

 <li>Total 12 output images (preferably rescale them to smaller size) (​<strong>Part A</strong>​) ● Charts comparing the performance (​<strong>Part B</strong>​, ​<strong>C</strong>​, and ​<strong>D</strong>​) ● Source code: ​c​, ​conv.py, ​ ​main.py​.</li>

 <li>Write a small report and put your code in ​&lt;your_purdue_username&gt;_HW&lt;0X&gt;​.pdf</li>

</ul>

<h1>API</h1>

Python:

Conv2D(in_channel, o_channel, kernel_size, stride, mode)

[int, 3D FloatTensor] Conv2D.forward(input_image)

Conv2D​ is a class and it has a ​forward​ function as one of its method (apart from its constructor).

C:

[int] c_conv(in_channel, o_channel, kernel_size, stride)

<h1>Instructions</h1>

<ol>

 <li>Class ​Conv2D​ must be defined in ​conv.py​ file with ​__init__()​ and forward()​ functions in it.</li>

</ol>

<h2>Part A</h2>

<ol start="2">

 <li>Initialize ​Conv2D​ in ​py​ (​conv2d​ = ​Conv2D(*args)​) for one of the task.</li>

 <li>Call ​forward() ​with your input image ​[3D FloatTensor]​. The ​forward() function must return output ​[int, 3D FloatTensor].​</li>

 <li>Save each channel of output tensor separately as a grayscale image in your main repository.</li>

 <li>Repeat 2-4 for all the three tasks.</li>

</ol>

<h2>Part B</h2>

<ol start="6">

 <li>Initialize ​Conv2D​ using values of Task 1 and set ​o_channel​ to 2^​<em>i</em>​ (​<em>i </em>​= 0, 1, …, 10) and ​mode​=’rand’.</li>

 <li>Plot the time taken for performing each ​forward()​ pass as a function of ​<em>i</em>​.</li>

</ol>

<h2>Part C</h2>

<ol start="8">

 <li>Initialize ​Conv2D​ using values of Task 2 with ​kernel_size​=3, 5, …, 11 and mode​=’rand’.</li>

 <li>Plot number of operations (​int​ returned by ​forward()​) used to perform convolution as a function of ​kernel_size​.</li>

</ol>

<h2>Part D</h2>

<ol start="10">

 <li>Repeat ​<strong>Part B</strong>​ using ​c_conv(*args) function which will be ​ ​C​ implementation of convolution.</li>

</ol>







<table width="548">

 <tbody>

  <tr>

   <td width="137"><strong> </strong></td>

   <td width="137"><strong>Task 1 </strong></td>

   <td width="137"><strong>Task 2 </strong></td>

   <td width="137"><strong>Task 3 </strong></td>

  </tr>

  <tr>

   <td width="137">in_channel</td>

   <td width="137">3</td>

   <td width="137">3</td>

   <td width="137">3</td>

  </tr>

  <tr>

   <td width="137">o_channel</td>

   <td width="137">1</td>

   <td width="137">2</td>

   <td width="137">3</td>

  </tr>

  <tr>

   <td width="137">kernel_size</td>

   <td width="137">3</td>

   <td width="137">5</td>

   <td width="137">3</td>

  </tr>

  <tr>

   <td width="137">stride</td>

   <td width="137">1</td>

   <td width="137">1</td>

   <td width="137">2</td>

  </tr>

  <tr>

   <td width="137">mode</td>

   <td width="137">‘known’</td>

   <td width="137">‘known’</td>

   <td width="137">‘known’</td>

  </tr>

  <tr>

   <td width="137">Kernel to use</td>

   <td width="137">K1</td>

   <td width="137">K4, K5</td>

   <td width="137">K1, K2, K3</td>

  </tr>

 </tbody>

</table>




<h1>Kernel definitions</h1>

K1 = [-1, -1, -1;  0, 0, 0;  1, 1, 1]

K2 = [-1,  0,  1; -1, 0, 1; -1, 0, 1]

K3 = [ 1,  1,  1;  1, 1, 1;  1, 1, 1]

K4 = [-1, -1, -1, -1, -1; -1, -1, -1, -1, -1; 0, 0, 0, 0, 0; 1, 1, 1, 1, 1; 1, 1, 1, 1, 1]

K5 = [-1, -1, 0, 1, 1; -1, -1, 0, 1, 1; -1, -1, 0, 1, 1; -1, -1, 0, 1, 1; -1, -1, 0, 1, 1]




<em>Known modes</em>​ mean use above kernel definitions. When you need to use only one kernel then use K1, for 2 kernels use K1-K2. When ​mode​=’rand’, initialize kernel with random values i.e. you do NOT need to use K1-K5.




For part B, C, and D; if your system is taking more than 1 hour then you do not need to go beyond that point (no need to further increase output channels or kernel size). Just mention it in your report that your system was taking too long to perform those computations and plot extrapolated results.

<h1>Format</h1>

Upload your homework on ​<em>Blackboard</em>​ as ​<strong>ZIP</strong>​ file.

Your folder name should be as following:

&lt;your_purdue_username&gt;_HW&lt;0X&gt;

For example, my folder name for first homework will look like ​aabhish_HW01​.




Please refrain from using global variables in your code unless it is specifically mentioned in the homework.




Results need to be described in the &lt;​ your_purdue_username&gt;_HW&lt;0X&gt;.pdf (eg.​        aabhish_HW01.pdf). Do ​    <strong>NOT</strong>​    forget to put all deliverables in your assignment folder.​




Keep in mind that <strong><u>your code might be made public after due date</u></strong><u>​         </u>. In case you have any​           problem with that then you should notify your instructor/TA beforehand.




Have fun! &#x1f600;



















<strong>NOTE:</strong>




My script will run something similar as the following to check whether you adhered to the given instructions.




from conv import Conv2D




# input_image = get image




conv2d = Conv2D(in_channel=3, o_channel=1, kernel_size=3, stride=1)

Number_of_ops, output_image = conv2d.forward(input_image)

Assert output_image.size() == expected_image.size()