# experiments
Nothing to see here. This is used for all kinds of experimentation and temporary work.

```cpp
void offset_game_projection_matrices(float offsetX, float offsetY)
{
  // In this simple example we only need to modify the projection matrix associated with the game camera. 
  // If the game is doing clever things like optimizing reflections or shadows based on projection matrix
  // then those code paths need to take a non-zero projection offset into account.

  // For nostalgia effect this game is using an old classic:
  D3DXMATRIX projection;
  D3DXMatrixPerspectiveFovRH(&projection, g_fov_radians, g_aspect, g_z_near, g_z_far)

  // Apply the offsets directly to the finished product (values are already normalized):
  projection._31 += offsetX;
  projection._32 += offsetY;

  // Update the games projection matrix:
  g_projection_matrix = projection;
}
``` 
