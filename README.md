import pygame
import random

# Ekran boyutları
SCREEN_WIDTH = 800
SCREEN_HEIGHT = 600
BLOCK_SIZE = 30

# Renkler
BLACK = (0, 0, 0)
WHITE = (255, 255, 255)
RED = (255, 0, 0)
GREEN = (0, 255, 0)
BLUE = (0, 0, 255)

# Şekiller ve renkleri
SHAPES = [
    [[1, 1, 1],
     [0, 1, 0]],

    [[0, 2, 2],
     [2, 2, 0]],

    [[3, 3],
     [3, 3]],

    [[0, 0, 0, 0],
     [4, 4, 4, 4],
     [0, 0, 0, 0]],

    [[0, 5, 0],
     [5, 5, 5],
     [0, 0, 0]],

    [[0, 6, 6],
     [6, 6, 0],
     [0, 0, 0]],

    [[7, 0, 0],
     [7, 7, 7],
     [0, 0, 0]]
]

SHAPES_COLORS = [RED, GREEN, BLUE, WHITE, BLACK, (255, 165, 0), (128, 0, 128)]

# Oyun alanı oluştur
def create_grid(locked_positions={}):
    grid = [[BLACK for _ in range(10)] for _ in range(20)]

    for i in range(len(grid)):
        for j in range(len(grid[i])):
            if (j, i) in locked_positions:
                c = locked_positions[(j, i)]
                grid[i][j] = c
    return grid

# Şekil oluştur
def create_shape():
    return random.choice(SHAPES)

# Şekil hareketi
def draw_shape(surface, shape, grid):
    for i in range(len(shape)):
        for j in range(len(shape[i])):
            if shape[i][j] != 0:
                pygame.draw.rect(surface, SHAPES_COLORS[shape[i][j] - 1],
                                 (j * BLOCK_SIZE, i * BLOCK_SIZE, BLOCK_SIZE, BLOCK_SIZE))
                pygame.draw.rect(surface, BLACK,
                                 (j * BLOCK_SIZE, i * BLOCK_SIZE, BLOCK_SIZE, BLOCK_SIZE), 1)

# Main fonksiyon
def main():
    pygame.init()

    screen = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))
    pygame.display.set_caption("Tetris")

    clock = pygame.time.Clock()
    fall_time = 0
    locked_positions = {}
    grid = create_grid(locked_positions)
    current_shape = create_shape()
    change_piece = False
    run = True

    while run:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                run = False

        # Şekil hareketi
        keys = pygame.key.get_pressed()
        if keys[pygame.K_LEFT]:
            current_shape.x -= 1
        if keys[pygame.K_RIGHT]:
            current_shape.x += 1
        if keys[pygame.K_DOWN]:
            current_shape.y += 1

        fall_time += clock.get_rawtime()
        clock.tick()

        # Şeklin düşmesi
        if fall_time > 1000:
            fall_time = 0
            current_shape.y += 1

        # Çizim işlemleri
        screen.fill(BLACK)
        draw_shape(screen, current_shape, grid)

        pygame.display.update()

    pygame.quit()

if __name__ == "__main__":
    main()
