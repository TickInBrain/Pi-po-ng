# Pi-po-ng
from pygame import *

window = display.set_mode((1184, 829))
display.set_caption('Пинг-понг')
background = transform.scale(image.load('хз.jpg'),(1184, 829))

class GameSprite(sprite.Sprite):
    def __init__(self, player_image, player_speed, player_x, player_y):
        super().__init__()
        self.image = transform.scale(image.load(player_image), (65, 65))
        self.speed = player_speed
        self.rect = self.image.get_rect()
        self.rect.x = player_x
        self.rect.y = player_y

    def reset(self):
        window.blit(self.image, (self.rect.x, self.rect.y))

class Player(GameSprite):
    def update_left(self):
        keys_pressed = key.get_pressed()
        if keys_pressed[K_w] and self.rect.y < 764:
            self.rect.y += self.speed
        if keys_pressed[K_s] and self.rect.y > 10:
            self.rect.y -= self.speed

    def update_right(self):
        keys_pressed = key.get_pressed()
        if keys_pressed[K_UP] and self.rect.y < 764:
            self.rect.y += self.speed
        if keys_pressed[K_DOWN] and self.rect.y > 10:
            self.rect.y -= self.speed

class Ball(GameSprite):
    def update(self):
        self.rect.y -= self.speed

player_1 = Player('racket.png', 10, 100, 415)
player_2 = Player('racket.png', 10, 1084, 415)

clock = time.Clock()
FPS = 60

run = True
finish = False
while run:
    for e in event.get():
        if e.type == QUIT:
            run = False
    if finish != True:
        window.blit(background,(0,0))
        player_1.update_left()
        player_2.update_right()
        player_1.reset()
        player_2.reset()
    display.update()

 
