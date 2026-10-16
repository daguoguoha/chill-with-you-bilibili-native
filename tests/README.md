# Bridge and decoder tests

Windows .NET Framework 4.x, Windows Media Foundation and the .NET 4.5 build of Newtonsoft.Json 13.0.3 are needed. Compile either test source together with source/Bridge.cs, Models.cs, NetworkErrors.cs and AudioDecoder.cs. Reference Newtonsoft.Json.dll, NAudio.Core.dll and NAudio.Wasapi.dll (2.2.1), QRCoder.dll (1.4.3 net35), System.Security.dll and the Framework netstandard.dll facade. Do not use Unity's Newtonsoft.Json build for a standalone process. Keep the dependency DLLs beside the executable.

Run BilibiliSmoke.exe rules for URL validation, short for a live b23.tv import, or without arguments for real QR generation/poll/cancel and public video download/decode. No QR is scanned. Run in an empty test directory, with no personal account data.

Run BilibiliLongTests.exe with one or more accessible long-video BV IDs. It downloads up to 64 MiB per item and decodes up to 1 GiB PCM, checks seek/EOF/disposal/cancellation, then removes its temporary PCM files. Select videos long enough to exceed the 128 MiB PCM memory threshold. It does not play audio or log stream URLs. This is a live integration test, not a guarantee that every video is playable.

Test-account folders are created beside the executable. Do not publish them, generated binaries, downloaded media, or local game assemblies. Actual in-game login, controls and installer validation are recorded in TESTING.md.
