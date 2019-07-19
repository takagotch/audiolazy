### audiolazy
---
https://github.com/danilobellini/audiolazy

```py
from audiolazy import *

from audiolazy.lazy_stream import Stream
from audiolazy import Stream

a = Stream(2, -2, -1)
b = Stream(3, 7, 5, 4)
c = a + b
c.take(15)

a = Stream([1, 2, 3, 2, 1])
b = Stream(3, 7, 5, 4)
c = a + b
list(c)

filt = 1 - z ** -1
filt
data = filt([.1, .2, .4, .3, -.1, -.3, -.2])
data
data *= 10
[int(round(x)) for x in data]
data_int = filt([1, 2, 4, 3, 2, -1, -3, -2], zero=0)
list(data_int)

(1 + z ** -2).plot().show()

(1 + z ** -2).plot().savefig("my_plot.pdf")

from matplotlib import pyplot as plt
filt = 1 + z ** -2
fig1 = filt.plot(plt.figure())
fig2 = filt.zplot(plt.figure())
plt.show()

filt1 = CascadeFilter(0.2 - z ** -3)
filt2 = CascadeFilter(1 / (1 -.8 * z ** -1 + .6 * z ** -2))
filt = (filt1 * 5 + filt2 * 10)
filt.zplot().show()

lpc([1, -2, 3, -4, -3, 2, -3, 2, 1], order=3).plot().show()

data = Stream(-1., 0., 1., 0.)
blk = data.take(200)
analysis_filt = lpc.covar(blk, 4)
analysis_filt
residual = list(analysis_filt(blk))
residual[:10]
synth_filt = 1 / analysis_filt
synth_filt(residual).take(10)
amplified_blk = list(Stream(blk) * -200)
synth_filt.plot(blk=amplified_blk).show()

rate = 44100
s, Hz = sHz(rate)
ms = 1e-3 * s
note1 = karplus_strong(440 * Hz)
note2 = zeros(300 * ms).append(karplus_strong(880 * Hz))
notes = (note1 + note2) * .5
sound = ntes.take(int(2 * s))
with AudioIO(True) as player:
  player.play(sound, rate=rate)
```

```sh
python setup.py install
pip install audiolazy
pip install -U .
pip install -U git+git://github.com/danilobellini/audiolazy.git
pip install -U git+git://github.com/danilobellini/audiolazy.git@0.04
```

```
```


