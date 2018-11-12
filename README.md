# GHDFS

Works with HDFS for common operations.

## Installation

Package is under com.globo.bigdata.ghdfs

Include in your dependencies:

```
    "com.globo.bigdata" %% "ghdfs" % "0.0.9"
```

## Usage

```
    val hdfs = HdfsManager(Properties.envOrNone("HADOOP_CONF_DIR"))
    
    hdfs.write(Path).write(String)
    
    hdfs.read(Path)
    
    hdfs.status(Path)
    
    hdfs.move(Path, Path)
    
    hdfs.listFiles(Path, recursive = false).foreach(...)
    
    hdfs.delete(Path, recursive = true)

    etc...
```

### Get Filesystem Instance

```
    hdfs.getFileSystem
```

### Use normal API
```
    val status = hdfs.getFileStatus(new Path("my_path.txt"))
    status.asInstanceOf[FileStatus].getPath.toString
```

# Tests

```bash
sbt test
```

# Deploy artifactory

```
sbt release
```

## Config for artifactory

```
cat ~/.sbt/.credentials

realm=Artifactory Realm
host=artifactory.globoi.com
user=LOGIN
password=SET YOURS
```

Where LOGIN is your artifactory login and password is the encrypted from page https://artifactory.globoi.com/artifactory/webapp/#/profile
