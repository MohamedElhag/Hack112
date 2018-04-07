import pygame
import random
import string

def mousePressed(x, y):
    if (((startScreen.p1Rect.center[0]-x)**2 + (startScreen.p1Rect.center[1]-y)**2)**.5)<=75:
        print ('you picked Luigi!')
    elif (((startScreen.p2Rect.center[0]-x)**2 + (startScreen.p2Rect.center[1]-y)**2)**.5)<=75:
        print ('you picked Mario!')
    elif (((startScreen.p3Rect.center[0]-x)**2 + (startScreen.p3Rect.center[1]-y)**2)**.5)<=75:
        print ('you picked Princess Peach!')

class StartScreen(pygame.sprite.Sprite):

    def __init__(self,width,height):
        self.bg = pygame.image.load("Bowser's_castle.png").convert_alpha()
        self.isTrue = True
        self.width = width
        self.height = height
        self.bgRect = self.bg.get_rect()
        self.bgRect.center = (250,250)
        self.text = 'Click anywhere to start'
        self.gameText = 'Choose Your Player:'
        self.xText = width/2
        self.yText = 3*height/4
        pygame.font.init()
        self.p1 = (pygame.transform.scale(pygame.image.load("luigiNSMBW.png").convert_alpha(),(100,150)))
        self.p2 = (pygame.transform.scale(pygame.image.load('mario.png').convert_alpha(),(110,175)))
        self.p3 = (pygame.transform.scale(pygame.image.load('peach.png').convert_alpha(),(100,150)))
        self.p1Rect = self.p1.get_rect()
        self.p2Rect = self.p2.get_rect()
        self.p3Rect = self.p3.get_rect()
        self.p1Rect.center = (100,250)
        self.p2Rect.center = (250,250)
        self.p3Rect.center = (400,250)
        
    def drawText(self,screen):
        myfont = pygame.font.SysFont('Times',30)
        textSurface = myfont.render(self.text,True,(255,255,255))

        textRect = textSurface.get_rect()
        textRect.center = (self.xText,self.yText)
        
        screen.blit(textSurface,textRect)
        
        gameFont = pygame.font.SysFont('Times',55)
        gameTextSurface = gameFont.render(self.gameText,True,(255,255,255))
        gameRect = gameTextSurface.get_rect()
        gameRect.center = (self.width/2,self.height/4)
        screen.blit(gameTextSurface,gameRect)
    
    def drawImage(self,screen):
        screen.blit(startScreen.bg,startScreen.bgRect)
        # pygame.draw.rect(screen, (0,200,200), (40,150,120,200))
        screen.blit(startScreen.p1,startScreen.p1Rect)
        screen.blit(startScreen.p2,startScreen.p2Rect)
        screen.blit(startScreen.p3,startScreen.p3Rect)
    

pygame.init()
screen = pygame.display.set_mode((500, 500))
clock = pygame.time.Clock()

startScreen = StartScreen(500,500)
playing = True
while playing:
    clock.tick(50)
    for event in pygame.event.get():
        if event.type == pygame.MOUSEBUTTONDOWN and event.button == 1:
            mousePressed(*event.pos)
        elif event.type == pygame.QUIT:
            playing = False
    if startScreen.isTrue:
        startScreen.drawImage(screen)
        startScreen.drawText(screen)
    else:
        screen.fill((255,255,255))
        
    pygame.display.flip()
pygame.quit()
