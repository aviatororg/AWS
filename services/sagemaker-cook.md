### Install Scala Jupyter Kernel

- get scala kernel
```
git clone https://github.com/jupyter-scala/jupyter-scala.git
cd jupyter-scala
```

- install coursier
```
curl -L -o coursier https://git.io/coursier-cli &&
    chmod +x coursier &&
    ./coursier --help
```

- install kernel

```
SCALA_VERSION=2.12.8 ALMOND_VERSION=0.2.1
./coursier bootstrap \
    -r jitpack \
    -i user -I user:sh.almond:scala-kernel-api_$SCALA_VERSION:$ALMOND_VERSION \
    sh.almond:scala-kernel_$SCALA_VERSION:$ALMOND_VERSION \
    --sources --default=true \
    -o almond

./almond --install
```

- now you can select kernel when starting a new notebook

# Sources
- https://github.com/awslabs/amazon-sagemaker-examples/issues/175
- https://get-coursier.io/docs/cli-overview
- http://almond-sh.github.io/almond/stable/docs/quick-start-install<Paste>
