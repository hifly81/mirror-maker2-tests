./kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 3 --partitions 3 --topic TopicA
./kafka-topics.sh --create --zookeeper localhost:3181 --replication-factor 3 --partitions 3 --topic TopicB

./kafka-topics.sh --list --zookeeper localhost:2181
./kafka-topics.sh --list --zookeeper localhost:3181


bin/kafka-producer-perf-test.sh \
  --topic test \
  --num-records 50000000 \
  --record-size 100 \
  --throughput -1 \
  --producer-props acks=1 \
  bootstrap.servers=localhost:9092 \
  buffer.memory=67108864 \
  batch.size=8196




./connect-mirror-maker.sh --help
./bin/connect-mirror-maker.sh mm2.properties


DC-Y.TopicB
DC-Y.checkpoints.internal
DC-Y.heartbeats
TopicA
__consumer_offsets
heartbeats
mm2-configs.DC-Y.internal
mm2-offset-syncs.DC-Y.internal
mm2-offsets.DC-Y.internal
mm2-status.DC-Y.internal


DC-X.TopicA
DC-X.checkpoints.internal
TopicB
__consumer_offsets
heartbeats
mm2-configs.DC-X.internal
mm2-offset-syncs.DC-X.internal
mm2-offsets.DC-X.internal
mm2-status.DC-X.internal
