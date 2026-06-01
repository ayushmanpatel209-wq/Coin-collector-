import pygame
import random

pygame.init()

WIDTH, HEIGHT = 800, 600
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Coin Collector")

player = pygame.Rect(375, 500, 50, 50)
coin = pygame.Rect(random.randint(0, 750), random.randint(0, 550), 25, 25)

score = 0
font = pygame.font.SysFont(None, 40)

clock = pygame.time.Clock()

running = True
while running:
    clock.tick(60)

    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    keys = pygame.key.get_pressed()

    if keys[pygame.K_LEFT]:
        player.x -= 5
    if keys[pygame.K_RIGHT]:
        player.x += 5
    if keys[pygame.K_UP]:
        player.y -= 5
    if keys[pygame.K_DOWN]:
        player.y += 5

    if player.colliderect(coin):
        score += 1
        coin.x = random.randint(0, 750)
        coin.y = random.randint(0, 550)

    screen.fill((30, 30, 50))

    pygame.draw.rect(screen, (0, 255, 0), player)
    pygame.draw.circle(screen, (255, 215, 0), coin.center, 12)

    text = font.render(f"Score: {score}", True, (255, 255, 255))
    screen.blit(text, (10, 10))

    pygame.display.flip()

pygame.quit()
