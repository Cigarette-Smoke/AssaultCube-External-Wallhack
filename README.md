# External ESP Cheat for Assault Cube

<img width="1916" height="978" alt="image" src="https://github.com/user-attachments/assets/74801027-b032-44a5-a5e9-847405d19a15" />

<img width="1917" height="985" alt="image" src="https://github.com/user-attachments/assets/4dba6bd5-8763-4710-921e-8f74e87d4597" />

# Basic Technical Overview:
1) The cheat continuously reads the positions of enemy models in Vector3 format by accessing the entity list through the Windows Native API function **NtReadVirtualMemory** 
2) It then converts these **world space coordinates** (Vector3) into **screen position coordinates** (Vector2) using a **W2S** (World To Screen) transformation formula
3) Finally, the ImGui library renders wallhack overlays at the calculated screen positions, displaying enemies through walls



# Static Addresses
- ``uint32_t dwViewMatrix = 0x0057DFD0;``



# Offsets
- ``uint32_t dwEntityList = CLIENT_BASE_ADDRESS + 0x18AC04;``
- ``auto dwPlayerCount = CLIENT_BASE_ADDRESS + 0x18AC0C;`` 
- ``uint32_t dwLocalPlayer = dwEntityList + 0x0017E0A8;``
- ``uint32_t player = dwEntityList + (PLAYER_COUNT_INDEX * 0x4);`` 
- ``uint32_t playerName = player + 0x205;``
- ``uint32_t playerHealth = player + 0xEC;``
- ``uint32_t playerPosX = player + 0x28;``
- ``uint32_t playerPosY = player + 0x2C;``
- ``uint32_t playerPosZ = player + 0x30;`` 
- ``uint32_t isDead = player + 0x0318;``

# Note
**Only supports Windows OS**
**Only works in Windowed mode** 

Last testing date: January 18th, 2025. 
Game Build: v1.3.0.2
