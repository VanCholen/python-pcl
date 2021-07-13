**⚠⚠ A new maintainer for this library is sought. Please see https://github.com/strawlab/python-pcl/issues/395. ⚠⚠**

.. raw:: html

    <a href="https://github.com/strawlab/python-pcl">
    <img style="position: absolute; top: 0; right: 0; border: 0;" src="https://s3.amazonaws.com/github/ribbons/forkme_right_darkblue_121621.png" alt="Fork me on GitHub"></a>

    <script type="text/javascript">
      var _gaq = _gaq || [];
      _gaq.push(['_setAccount', 'UA-3707626-7']);
      _gaq.push(['_trackPageview']);
      (function() {
        var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true;
        ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js';
        var s = document.getElementsByTagName('script')[0]; s.parentNode.insertBefore(ga, s);
      })();
    </script>

    <div align="center"><img src="docs/image/pcl_logo_958x309.png" width="309"/></div>

Introduction
============

This is a small python binding to the `pointcloud <http://pointclouds.org/>`_ library.
Currently, the following parts of the API are wrapped (all methods operate on PointXYZ)
point types

 * I/O and integration; saving and loading PCD files
 * segmentation
 * SAC
 * smoothing
 * filtering
 * registration (ICP, GICP, ICP_NL)

The code tries to follow the Point Cloud API, and also provides helper function
for interacting with NumPy. For example (from tests/test.py)

.. code-block:: python

    import pcl
    import numpy as np
    p = pcl.PointCloud(np.array([[1, 2, 3], [3, 4, 5]], dtype=np.float32))
    seg = p.make_segmenter()
    seg.set_model_type(pcl.SACMODEL_PLANE)
    seg.set_method_type(pcl.SAC_RANSAC)