# http_gpu
Massively many-core HTTP server on bitsliced GPU

TODO: Implement RISC-V R32I Instruction set.
TODO: Implement hart to hart communication.
TODO: Implement HTTP ingress and egress.
TODO: Implement database to be served over HTTP.
TODO: Publish dataset to be served over HTTP.
TODO: Keep dataset updated.

## Implementing R32I ISA:
Emulate program counter, program stream, data RAM, immediate and register file.
JUMP/BRANCH: Update PC.
LOAD: Read data block from emulated RAM and update register file.
STORE: Write data block to emulated RAM.
ALU: Update register file.

## Hart to Hart comm:
Flag register to hold open communication lines.
Use thread sync primitives to distribute data.
Communication should achieve a few megabaud.  Emulate queue?

## HTTP Ingress:
HTTP will be used to request data (GET), and update database (PUT/POST)
Parse HTTP over Unix socket with R32I ISA.

## HTTP Egress:
HTTP Responses to data GETs and database updates.
Use templates, and update templates with R32I ISA.

## Database:
Hosted on disk.
Use high performance disk and socket access to highlight GPU performance.
Update database from remote RPC.
