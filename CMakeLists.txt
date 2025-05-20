cmake_minimum_required(VERSION 3.10.0)
project(Retro_Shooter VERSION 0.1.0 LANGUAGES C CXX)

add_executable(Retro_Shooter Ammo.cpp Coin.cpp Game.cpp Health.cpp Level.cpp MathAddon.cpp Pickup.cpp Projectile.cpp SoundLoader.cpp Sprite.cpp TextureLoader.cpp Timer.cpp Unit.cpp UnitEnemy.cpp UnitPlayer.cpp UpgradeAmmo.cpp UpgradeHealth.cpp UpgradeWeaponSpeed.cpp Vector2D.cpp Weapon.cpp main.cpp)

find_package(SDL2 REQUIRED)
find_package(SDL2_mixer REQUIRED)
    if(SDL2_mixer_FOUND)
      include_directories(${SDL2_mixer_INCLUDE_DIRS})
      target_link_libraries(Retro_Shooter PRIVATE SDL2 SDL2_mixer::SDL2_mixer SDL2_image ${SDL2_mixer_LIBRARIES})
    else()
      message(FATAL_ERROR "SDL2_mixer not found")
    endif()

target_include_directories(Retro_Shooter PRIVATE include SDL2_mixer)