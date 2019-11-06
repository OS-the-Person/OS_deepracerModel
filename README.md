# OS_deepracerModel
This is an AWS DeepRacer model, trained on AWS Console for the AWS DeepRacer Competition

The reward function is a basic template that can produce results on any track with 3 to 5 hours of training.

//Reward Function
def reward_function(params):

    if params['all_wheels_on_track']:
        reward = params['progress']
    else:
        reward = 0.00001  //some very small value

    return float(reward)
    

### Hyperparameters Used
At initial training with above reward function, I trained with default hyperparameters
But as the model got better, increasing the **number of experience episodes between each policy-updating iteration**
produced positive results

### Action space 
The action space of this model
Steering angle:: 30 degrees
Steering angle granularity:: 5
Max Speed:: 6 m/s
Speed graularity:: 3

Results:: after 4 hours of transfer learning anchieved 00:00:22.678 on re:invent 2018 track
