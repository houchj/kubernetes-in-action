###   Issues in this Chapter

## 1. the busybox image can not be started up, because the request memory and cpu are too small,
<p>change to following: <br>
    resources:
      requests:
        cpu: 150m
        memory: 1000Ki
      limits:
        cpu: 1000m
        memory: 40Mi
</p>

### 2. 


