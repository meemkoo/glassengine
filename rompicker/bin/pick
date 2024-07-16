#!/bin/python3
import sys

try:
    infile = sys.argv[1]
    outdir = sys.argv[2]
except Exception:
    print("Bad arguments")
    quit(-1)

rom = open(infile, 'rb').read()

def divide_chunks(list_, size):
    for i in range(0, len(list_), size): 
        yield list_[i:i + size]

divided = list(divide_chunks(rom, 0x4000))

for i, c in enumerate(divided):
    handle = open(f'./{outdir}/{i}_{hex(i)}.rom', 'wb')
    handle.write(c)
    handle.close()
