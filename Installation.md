# Installation

Download the latest binary from this [downloads page](https://kafka.apache.org/downloads)

## Mac

Move the downloaded binary to your home directory

```sh
mv Downloads/kafka_2.12-3.4.0.tgz .
```

Untar it using the following command

```sh
tar -xvf kafka_2.12-3.4.0.tgz
```

Export the PATH. Open `.bash_profile` or `.zshrc` according to the current environment you are using `nano .zshrc` or `code .zshrc` (whichever is comfortable for you)

```sh
export PATH="$PATH:$HOME/kafka_2.12-3.4.0/bin"
```

OPTIONAL: If you wish not to use `.sh` while running the commands install Kafka using homebrew

```sh
brew install kafka
```

To easily access the config files while running Kafka and Zookeeper, export the configuration file as environemnt variables. In the `.bash_profile` or `.zshrc` file, you can add the following

```sh
export ZOOKEEPER_CONFIG=$HOME/kafka_2.12-3.4.0/config/zookeeper.properties
export KAFKA_CONFIG=$HOME/kafka_2.12-3.4.0/config/server.properties
```

Edit the both the configuration files to save the logs and supporting files in a specified directory rather than the temp directory as default.

```sh
cd kafka_2.12-3.4.0
mkdir data/zookeeper
mkdir data/kafka
```

After creating theese directories alter the `kafka_2.12-3.4.0/config/server.properties` file to point to the new directory

```sh
log.dirs=/Users/<YOUR USERNAME>/kafka/data/kafka
```

In the `zookeeper.properties`

```sh
dataDir=/Users/<YOUR USERNAME>/kafka/data/zookeeper
```
