# Cartoon-animation
This is my first repository
import pygame
import sys

# Initialize Pygame
pygame.init()

# Set up the display
screen_width = 800
screen_height = 600
screen = pygame.display.set_mode((screen_width, screen_height))
pygame.display.set_caption("Simple Cartoon Animation")

# Define colors
white = (255, 255, 255)
blue = (0, 0, 255)

# Define a simple character as a rectangle
character_width = 50
character_height = 60
character_x = 0
character_y = screen_height - character_height - 50
character_speed = 5

# Clock to control the frame rate
clock = pygame.time.Clock()

# Main animation loop
while True:
    # Handle events
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    # Update character position
    character_x += character_speed
    if character_x > screen_width:
        character_x = -character_width

    # Fill the screen with white
    screen.fill(white)

    # Draw the character
    pygame.draw.rect(screen, blue, (character_x, character_y, character_width, character_height))

    # Update the display
    pygame.display.flip()

    # Cap the frame rate at 60 FPS
    clock.tick(60)
