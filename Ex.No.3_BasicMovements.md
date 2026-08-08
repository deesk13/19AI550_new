Ex.No: 2 Basic movements in Unity
DATE:08-08-26
REGISTER NUMBER : 212223240026
AIM:
To learn the basic movements translation,scaling and rotation of game objects through code.

Procedure:
Setup the Scene
Open Unity and create a 3D Scene.
Add three objects:Cube → Rename to Object1 (for movement),Sphere → Rename to Object2 (for rotation).Capsule → Rename to Object3 (for scaling).
Add the Script,Create a C# Script → Name it TransformOperations.cs.
Write the code for translation,scaling and rotation,save and close the script
Save the script
Select any empty GameObject (or create one: GameObject → Create Empty).
Attach the TransformOperations script to it.
In the Inspector, assign Object1 → Drag the Cube,Object2 → Drag the Sphere.Object3 → Drag the Capsule.
Run the Scene Press Play ▶️ in Unity
Stop the program.
Program
using UnityEngine;
public class TransformOperations : MonoBehaviour
{
    public Transform object1; // Object for translation
    public Transform object2; // Object for rotation
    public Transform object3; // Object for scaling

    public float moveSpeed = 2f;  // Speed of translation
    public float rotateSpeed = 50f; // Speed of rotation
    public float scaleSpeed = 0.5f; // Speed of scaling

    void Update()
    {
        // Translate (Move) object1 along the X-axis- Time.deltaTime to make movement smooth across all frame rates
        if (object1 != null)
        {
            object1.position += Vector3.right * moveSpeed * Time.deltaTime;
        }

        // Rotate object2 around the Y-axis
        if (object2 != null)
        {
            object2.Rotate(Vector3.up * rotateSpeed * Time.deltaTime);
        }

        // Scale object3 up and down
        if (object3 != null)
        {
            float scaleChange = Mathf.PingPong(Time.time * scaleSpeed, 1f) + 0.5f; // generates a value that moves back and forth between 0 and length
            object3.localScale = new Vector3(scaleChange, scaleChange, scaleChange);
        }
    }
}
Output:
<img width="933" height="567" alt="image" src="https://github.com/user-attachments/assets/bff3e05c-f4d2-469a-af9d-79bdc21a32b6" />

<img width="935" height="512" alt="image" src="https://github.com/user-attachments/assets/5b853306-9798-45d8-9a66-34a5abe2b5a7" />


Result:
Thus the basic movement is learned through scripting
