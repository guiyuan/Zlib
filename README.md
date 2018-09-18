# Zlib
c# zlib压缩解压缩内存数据

# 压缩数据
```
    public static byte[] compress(byte[] data)
    {
        using (var ms = new MemoryStream())
        {
            Stream steam = new ZlibStream(ms, CompressionMode.Compress, CompressionLevel.BestCompression);
            ZlibBaseStream.CompressBuffer(data, steam);
            
            return ms.ToArray();
        }
    }
 ```   
   
# 解壓縮數據
```
    public static byte[] deCompress(byte[] data)
    {
        using (var ms = new MemoryStream(data))
        {
            Stream stream = new ZlibStream(ms, CompressionMode.Decompress);
            return ZlibBaseStream.UncompressBuffer(data, stream);
        }
    }
```
