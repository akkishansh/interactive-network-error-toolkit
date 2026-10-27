# Interactive Network Error Detection and Correction Toolkit

A self-contained browser-based educational simulator. Open index.html in Chrome, Edge, or Brave. It works without Python or an installation; an internet connection is only needed for the external standards links and optional web fonts.

## Project Explanation Video
[Watch or download the video](https://github.com/akkishansh/interactive-network-error-toolkit/releases/tag/v1.0.0)

## How to use
1. Enter a short message, such as A or HELLO.
2. Choose an error location: no error, a message data bit, a check bit, or any frame bit.
3. Select Parity, Checksum, CRC-8, or Hamming (7,4), then click **Build frame**.
4. Click an enabled blue or gold bit to deliberately flip it. Click it again to undo that flip.
5. Use **Next step** or **Play walkthrough** to follow the sender, channel, and receiver.
6. Read **Internal Simulation Trace** to inspect the sender calculations, transmitted frame, bit changes, receiver calculation, and final result.
7. Open **Real-world protocols** to compare the teaching models with Ethernet, TCP, UDP, and TLS 1.3.

## What the model shows
- Parity adds one even-parity bit.
- The checksum is an 8-bit one’s-complement teaching model.
- CRC-8 uses generator 100000111 (polynomial x^8 + x^2 + x + 1). The trace shows XOR long division.
- Hamming (7,4) groups four message bits into seven-bit codewords. The three check bits are in positions 1, 2, and 4; the trace shows syndrome calculation and the locally corrected frame.
- Hamming can correct a supported single-bit error without retransmission. The receiver still calculates the syndrome and corrects its local copy. Multiple errors in one codeword are not safely correctable.
- In Hamming mode, check bits are interleaved within each codeword and shown in gold.
- Clicking a bit injects an error directly into the frame in software. This does not simulate electrical noise, radio interference, physical cables, or real packet transmission.
- The app does not implement TCP, UDP, Ethernet, TLS, encryption, or live packet capture.
- The message input is limited to 12 characters to keep the bit-level trace readable.

## Standards references
- TCP: https://www.rfc-editor.org/rfc/rfc9293.html
- UDP: https://www.rfc-editor.org/rfc/rfc768.html
- TLS 1.3: https://www.rfc-editor.org/rfc/rfc8446.html
