# RAFT

## Abstract

<!-- [ABSTRACT] -->

We introduce Recurrent All-Pairs Field Transforms (RAFT),
a new deep network architecture for optical flow. RAFT extracts perpixel
features, builds multi-scale 4D correlation volumes for all pairs
of pixels, and iteratively updates a flow field through a recurrent unit
that performs lookups on the correlation volumes. RAFT achieves state-
of-the-art performance. On KITTI, RAFT achieves an F1-all error of
5.10%, a 16% error reduction from the best published result (6.10%).
On Sintel (final pass), RAFT obtains an end-point-error of 2.855 pixels,
a 30% error reduction from the best published result (4.098 pixels). In
addition, RAFT has strong cross-dataset generalization as well as high
efficiency in inference time, training speed, and parameter count. Code
is available at https://github.com/princeton-vl/RAFT.

<!-- [IMAGE] -->

<div align=center>
<img src="https://user-images.githubusercontent.com/76149310/142731339-c1978af7-c9de-4b21-9d6c-e786daff9601.png" width="70%"/>
</div>

## Citation

<!-- [ALGORITHM] -->

```bibtex
@inproceedings{teed2020raft,
  title={Raft: Recurrent all-pairs field transforms for optical flow},
  author={Teed, Zachary and Deng, Jia},
  booktitle={European conference on computer vision},
  pages={402--419},
  year={2020},
  organization={Springer}
}
```

## Results and Models

<table>
    <thead>
        <tr>
            <td rowspan=2>Models</td>
            <td rowspan=2>Training datasets</td>
            <td rowspan=2>Flying Chairs</td>
            <td colspan=2>Sintel(training)</td>
            <td colspan=2>KITTI2015(training)</td>
            <td rowspan=2>Log</td>
            <td rowspan=2>Config</td>
            <td rowspan=2>Download</td>
        </tr>
        <tr>
            <th>clean</th>
            <th>final</th>
            <th>Fl-all</th>
            <th>EPE</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th>RAFT</th>
            <th>Flying Chairs</th>
            <th>0.78</th>
            <th>2.54</th>
            <th>5.32</th>
            <th>-</th>
            <th>-</th>
            <th><a href='https://download.openmmlab.com/mmflow/raft/raft_8x2_100k_flyingchairs.log.json'>log</a></th>
            <th><a href='https://download.openmmlab.com/mmflow/raft/raft_8x2_100k_flyingchairs.py'>Config</a></th>
            <th><a href='https://download.openmmlab.com/mmflow/raft/raft_8x2_100k_flyingchairs.pth'>Model</a></th>
        </tr>
        <tr>
            <th>RAFT</th>
            <th>FlyingChairs + FlyingThing3d</th>
            <th>-</th>
            <th>1.46</th>
            <th>2.67</th>
            <th>15.07%</th>
            <th>4.52</th>
            <th><a href='https://download.openmmlab.com/mmflow/raft/raft_8x2_100k_flyingthings3d_400x720.log.json'>log</a></th>
            <th><a href='https://download.openmmlab.com/mmflow/raft/raft_8x2_100k_flyingthings3d_400x720.py'>Config</a></th>
            <th><a href='https://download.openmmlab.com/mmflow/raft/raft_8x2_100k_flyingthings3d_400x720.pth'>Model</a></th>
        </tr>
        <tr>
            <th>RAFT</th>
            <th>FlyingChairs + FlyingThing3d + Sintel</th>
            <th>-</th>
            <th>0.60</th>
            <th>0.98</th>
            <th>-</th>
            <th>-</th>
            <th><a href='https://download.openmmlab.com/mmflow/raft/raft_8x2_100k_flyingthings3d_sintel_368x768.log.json'>log</a></th>
            <th><a href='https://download.openmmlab.com/mmflow/raft/raft_8x2_100k_flyingthings3d_sintel_368x768.py'>Config</a></th>
            <th><a href='https://download.openmmlab.com/mmflow/raft/raft_8x2_100k_flyingthings3d_sintel_368x768.pth'>Model</a></th>
        </tr>
        <tr>
            <th>RAFT</th>
            <th>Mixed Dataset<sup>[1]</sup></th>
            <th>-</th>
            <th>0.61</th>
            <th>1.03</th>
            <th>5.74%</th>
            <th>1.70</th>
            <th><a href='https://download.openmmlab.com/mmflow/raft/raft_8x2_100k_mixed_368x768.log.json'>log</a></th>
            <th><a href='https://download.openmmlab.com/mmflow/raft/raft_8x2_100k_mixed_368x768.py'>Config</a></th>
            <th><a href='https://download.openmmlab.com/mmflow/raft/raft_8x2_100k_mixed_368x768.pth'>Model</a></th>
        </tr>
    </tbody>
</table>

[1] The mixed dataset consisted of FlyingChairs, FlyingThing3d, Sintel, KITTI2015, and HD1K.
