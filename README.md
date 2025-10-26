# 🎮 btlsnk-sim

btlsnk-sim clone you can run locally

![Python](https://img.shields.io/badge/python-3.10-blue)

## what

write snake ai in any language, test without internet

compatible with btlsnk-sim api

## install

```bash
pip install btlsnk-sim
```

## run game

```bash
btlsnk-sim game \
  --snakes http://localhost:8000,http://localhost:8001 \
  --width 11 \
  --height 11
```

opens web viewer at `http://localhost:3000`

## create snake

```python
# mysnake.py
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route('/move', methods=['POST'])
def move():
    data = request.json
    # your logic here
    return jsonify({'move': 'up'})

if __name__ == '__main__':
    app.run(port=8000)
```

## game modes

- standard
- royale (shrinking board)
- squad (team play)

## features

- game replay
- step-by-step debugger
- latency simulation
- custom board layouts

## example bots

`examples/` folder:

- `random_snake.py` - moves randomly
- `smart_snake.py` - avoids walls and self
- `aggressive_snake.py` - chases nearest enemy

## cli

```bash
# tournament mode
btlsnk-sim tournament \
  --snakes snake1,snake2,snake3,snake4 \
  --rounds 10

# replay
btlsnk-sim replay game-2024-03-15.json
```

## api

same as btlsnk-sim:

```
POST /start
POST /move
POST /end
```

docs: [docs.btlsnk-sim](https://docs.btlsnk-sim)

## troubleshooting

**snake not responding?**
check snake server is running and accessible

**game stuck?**
check snake returns response within 500ms

**visual glitches?**
update browser or use chrome

MIT • not affiliated with other

# PR Merge: 2025-10-26 13:35:50

# PR Merge: 2025-10-26 13:36:08

# PR Update: 2025-10-26 13:37:31
