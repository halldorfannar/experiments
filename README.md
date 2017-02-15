# experiments
Nothing to see here. This is used for all kinds of experimentation and temporary work.

```cpp
if (g_isAnselSessionActive)
{
  ansel::Camera cam;
  cam.fov = get_game_fov_degrees();
  cam.position = {game_cam_position.x, game_cam_position.y, game_cam_position.z};
  cam.rotation = {game_cam_orientation.x, game_cam_orientation.y, game_cam_orientation.z, game_cam_orientation.w};

  ansel::updateCamera(cam);
  // This is where a game would typically perform collision detection
  // and adjust the values requested by player in cam.position 

  game_cam_position = {cam.position.x, cam.position.y, cam.position.z};
  game_cam_orientation = {cam.rotation.x, cam.rotation.y, cam.rotation.z, cam.rotation.w};

  set_game_fov_degrees(cam.fov);

  // modify projection matrices by the offset amounts
  offset_game_projection_matrices(cam.projectionOffsetX, cam.projectionOffsetY);
}
``` 
