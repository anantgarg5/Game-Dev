using UnityEngine;
using System.Collections;

public class DroneMovementScript : MonoBehaviour {
	Rigidbody ourDrone;

	void Awake(){
		ourDrone= GetComponent<Rigidbody>();
	}

	void FixedUpdate(){
		MovementUpDown();
		MovementForward();
		ourDrone.AddRelativeForce(Vector3.up * upForce);

	}

	public float upForce;
	void MovementUpDown(){
		if(Input.GetKey(KeyCode.I)){
			upForce =450;
		}
		else if(Input.GetKey(KeyCode.K)){
			upForce=-200;
		}
		else if(!Input.GetKey(KeyCode.I) && !Input.GetKey(KeyCode.K)){
			upForce = 98.1;
		}
	}

	private float movementForwardSpeed =50.0f;
	private float tiltAmountForward = 0;               //confirm 

	void MovementForward(){

	}
}
