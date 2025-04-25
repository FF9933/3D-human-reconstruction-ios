# (VERY FAST) 3D - Human Pose Reconstruction using one image and a config picture 
(Alpha and Beta Angles are extracted)
# Alpha Angle Calc
It is assumed in the work that each part of a body
is connected to another and is fixed at a certain point, i.e. a circle is the maximum movement when the movement is parallel
to the camera. This is shown graphically below:
\

![image](https://github.com/user-attachments/assets/2b4e0f72-5f4b-479a-aa9a-94a971306ce7)

Figure 2 shows that a circle becomes an ellipse
when it is rotated towards the camera. Seen from above,
can now be calculated using the cosine.
\

<img width="551" alt="Screenshot 2025-04-25 at 19 01 51" src="https://github.com/user-attachments/assets/399363b6-d0e9-41f7-87fe-40eb4cbf03c6" />


The following problem now arises: the shortest distance from the
center of the ellipse cannot be determined in Figure 1.
. This means that the arc cosine function cannot yet be formed.
Instead, however, we know the X and Y
values noted in the camera image (distance EF and FM, where M is the center [0,0,0]):
In addition, we can see the distance EF and GH, which is the same distance from the center point M when viewed from above
. An important observation
is that G and E are equidistant from the center point in the bird's eye view
and that |EF| = |GH| applies.
\

<img width="551" alt="Screenshot 2025-04-25 at 19 03 27" src="https://github.com/user-attachments/assets/f73953e5-4902-46be-85fa-0fcef58872a5" />

Since EF = Y-value of the camera image

\

<img width="551" alt="Screenshot 2025-04-25 at 19 04 46" src="https://github.com/user-attachments/assets/f5fcd552-50fe-4dea-9416-9a358df93664" />


Another finding is that the X value of the camera image can be read directly. This is FM. 
\

<img width="551" alt="Screenshot 2025-04-25 at 19 05 40" src="https://github.com/user-attachments/assets/e16d43e7-98de-4f60-b53a-306aae81778a" />

We also know the radius r of the original circle with center
M:
\

<img width="551" alt="Screenshot 2025-04-25 at 19 06 37" src="https://github.com/user-attachments/assets/84cddce7-d72b-463c-8d5b-b8894ac453a1" />


Now HM can be calculated using the Pythagorean theorem:
\

<img width="551" alt="Screenshot 2025-04-25 at 19 11 58" src="https://github.com/user-attachments/assets/e7e75c64-1d76-459f-b01e-1b348f7b4fcb" />

The arc cosine can now be calculated:
\

<img width="551" alt="Screenshot 2025-04-25 at 19 11 09" src="https://github.com/user-attachments/assets/693caadb-0877-4231-94ef-8139de6657f5" />

