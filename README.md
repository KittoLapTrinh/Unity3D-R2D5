# Unity3D-R2D5

# Prefabs
![image](https://github.com/user-attachments/assets/9a745dbb-284f-4049-a178-589742ced31f)
# R2D5Controller:
~~~
using UnityEngine;
using UnityEngine.AI;

public class R2D5Controller : MonoBehaviour
{
    private NavMeshAgent agent;

    void Start()
    {
        agent = GetComponent<NavMeshAgent>();
    }

    void Update()
    {
        // Điều khiển di chuyển bằng bàn phím
        Vector3 moveDirection = Vector3.zero; // Khởi tạo vector di chuyển

        if (Input.GetKey(KeyCode.W))
        {
            moveDirection += Vector3.forward; // Di chuyển về phía trước
        }
        if (Input.GetKey(KeyCode.S))
        {
            moveDirection += Vector3.back; // Di chuyển về phía sau
        }
        if (Input.GetKey(KeyCode.A))
        {
            moveDirection += Vector3.left; // Di chuyển sang trái
        }
        if (Input.GetKey(KeyCode.D))
        {
            moveDirection += Vector3.right; // Di chuyển sang phải
        }

    // Di chuyển đối tượng nếu có hướng di chuyển
    if (moveDirection != Vector3.zero)
    {
        transform.Translate(moveDirection * Time.deltaTime * 5f, Space.World);
    }
}


    // Hàm cho robot di chuyển đến vị trí
    public void MoveToPosition(Vector3 target)
    {
        agent.SetDestination(target);
    }
}

~~~

