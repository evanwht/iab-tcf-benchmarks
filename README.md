# iab-tcf String Decoding Benchmarks

Benchmarks for iab tcf string decoding and encoding

Versions tested:

- original 
- sleiman/v2-implementation
    - evanwht1/bitvectorWithPosition
    - evanwht1/internalizeSets
    - evanwht1/fieldsWithOffsets
    - laktech/v2-lazy-segment-input-stream
        - evanwht1/lazy-input
    - sleiman/single-scan
        - evanwht1/single-scan
    
## Environment

- Macbook Pro 2015
- 2.2 Ghz Intel i7
- 16 GB 1600 MHz DDR3
- JDK 11.0.1
- jmh 1.23
- 10 warmup iterations + 10 measurement iterations
- 4 threads + 1 fork

## How To User

If you would like to run these benchmarks your self, choose which version you would like and modify the pom to import
that version. You may need to modify the [MyBenchmark](src/main/java/org/sample/MyBenchmark.java) class.

You can change the options defined in the main method but be sure to keep those consistent between runs of different
versions. Finally, run the main method and jmh will start running the 3 benchmarks. The current options tend to take
around 20 minutes to complete one version.

## Results

Decoding of the Core String Only  
![](resources/Core-Only.png)

Decoding of a Core String and a Publisher TC Segment
![](resources/Core-Publisher.png)

Decoding of a full 4 segment string (Core String, OOB disclose + allowed Vendors, and publisher tc)
![](resources/Full.png)


