# JenkinsEmailTemplate
This is a modified email template provided by email-ext-plugin with a better look and information
``` ini

BenchmarkDotNet=v0.10.14, OS=Windows 10.0.16299.547 (1709/FallCreatorsUpdate/Redstone3)
Intel Core i5-6300U CPU 2.40GHz (Skylake), 1 CPU, 4 logical and 2 physical cores
Frequency=2437499 Hz, Resolution=410.2566 ns, Timer=TSC
.NET Core SDK=2.1.300
  [Host]     : .NET Core 2.1.0 (CoreCLR 4.6.26515.07, CoreFX 4.6.26515.06), 64bit RyuJIT  [AttachedDebugger]
  DefaultJob : .NET Core 2.1.0 (CoreCLR 4.6.26515.07, CoreFX 4.6.26515.06), 64bit RyuJIT


```
|                Method |      Categories |              Mean |              Error |             StdDev |            Median |               Min |               Max | Scaled | ScaledSD |  Gen 0 | Allocated |
|---------------------- |---------------- |------------------:|-------------------:|-------------------:|------------------:|------------------:|------------------:|-------:|---------:|-------:|----------:|
| DeSerializeNewtonSoft | Deserialization | 759,340,387.28 ns | 15,781,419.4632 ns | 45,279,850.7672 ns | 734,289,535.44 ns | 722,955,684.63 ns | 907,930,786.16 ns |   1.00 |     0.00 |      - |       0 B |
|    DeSerializeNetJSON | Deserialization | 740,802,272.24 ns | 14,628,767.2290 ns | 23,622,732.2646 ns | 730,556,319.32 ns | 722,095,777.39 ns | 807,122,735.35 ns |   0.98 |     0.06 |      - |       0 B |
|   DeSerializeFastJSON | Deserialization |                NA |                 NA |                 NA |                NA |                NA |                NA |      ? |        ? |    N/A |       N/A |
|        DeSerializeJil | Deserialization | 766,234,172.39 ns | 14,968,228.3866 ns | 18,382,328.6897 ns | 761,475,186.76 ns | 745,332,333.98 ns | 805,876,769.08 ns |   1.01 |     0.06 |      - |       0 B |
|                       |                 |                   |                    |                    |                   |                   |                   |        |          |        |           |
|   SerializeNewtonSoft |   Serialization |          62.85 ns |          0.5880 ns |          0.5500 ns |          62.92 ns |          61.84 ns |          63.70 ns |   1.00 |     0.00 | 0.0254 |      40 B |
|      SerializeNetJSON |   Serialization |          63.45 ns |          1.4920 ns |          1.3226 ns |          63.55 ns |          61.41 ns |          66.42 ns |   1.01 |     0.02 | 0.0254 |      40 B |
|     SerializeFastJSON |   Serialization |         127.89 ns |          1.5885 ns |          1.4858 ns |         127.70 ns |         124.72 ns |         130.27 ns |   2.03 |     0.03 | 0.1423 |     224 B |
|          SerializeJil |   Serialization |          94.13 ns |          1.4484 ns |          1.3548 ns |          94.60 ns |          92.03 ns |          96.79 ns |   1.50 |     0.02 | 0.1525 |     240 B |

Benchmarks with issues:
  BenchmarkExecutorLargeDataSet.DeSerializeFastJSON: DefaultJob
