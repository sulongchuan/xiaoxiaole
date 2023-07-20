# xiaoxiaole
import pygame  
import random  
  
# 定义常量  
SCREEN_WIDTH = 600  
SCREEN_HEIGHT = 800  
ROW_COUNT = 10  
COLUMN_COUNT = 10  
SQUARE_SIZE = (SCREEN_WIDTH // COLUMN_COUNT, SCREEN_HEIGHT // ROW_COUNT)  
COLORS = [(255, 0, 0), (0, 255, 0), (0, 0, 255)]  
  
# 初始化 Pygame  
pygame.init()  
  
# 创建游戏窗口  
screen = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))  
pygame.display.set_caption("消消乐")  
  
# 创建方块列表  
blocks = []  
for i in range(ROW_COUNT):  
    row = []  
    for j in range(COLUMN_COUNT):  
        color = random.choice(COLORS)  
        square = pygame.Surface(SQUARE_SIZE)  
        square.fill(color)  
        row.append(square)  
    blocks.append(row)  
  
# 游戏循环  
running = True  
while running:  
    # 处理事件  
    for event in pygame.event.get():  
        if event.type == pygame.QUIT:  
            running = False  
  
    # 绘制方块  
    for i in range(ROW_COUNT):  
        for j in range(COLUMN_COUNT):  
            screen.blit(blocks[i][j], (j * SQUARE_SIZE[0], i * SQUARE_SIZE[1]))  
  
    # 更新屏幕  
    pygame.display.update()  
  
# 退出 Pygame  
pygame.quit()
