[文档](https://zhuanlan.zhihu.com/p/50683232) [GitHub-docker-android](https://github.com/budtmo/docker-android)

```bash
docker run --privileged -d -p 6080:6080 -p 5554:5554 -p 5555:5555 -e DEVICE="Nexus 5" --name android-container butomo1989/docker-android-x86-7.1.1
```