# <img src="/src/icon.png" height="30px"> Verify.ImageSharp

[![Build status](https://ci.appveyor.com/api/projects/status/o30f8u47l7vv5844?svg=true)](https://ci.appveyor.com/project/SimonCropp/Verify-ImageSharp)
[![NuGet Status](https://img.shields.io/nuget/v/Verify.ImageSharp.svg)](https://www.nuget.org/packages/Verify.ImageSharp/)

Extends [Verify](https://github.com/VerifyTests/Verify) to allow verification of documents via [ImageSharp](https://github.com/SixLabors/ImageSharp).


## NuGet package

https://nuget.org/packages/Verify.ImageSharp/


## Usage

Given a test with the following definition:

<!-- snippet: TestDefinition -->
<a id='snippet-testdefinition'></a>
```cs
[TestFixture]
public class Samples
{
    static Samples()
    {
        VerifyImageSharp.Initialize();
    }
```
<sup><a href='/src/Tests/Samples.cs#L4-L14' title='Snippet source file'>snippet source</a> | <a href='#snippet-testdefinition' title='Start of snippet'>anchor</a></sup>
<!-- endSnippet -->


### Verify a file

<!-- snippet: VerifyImageFile -->
<a id='snippet-verifyimagefile'></a>
```cs
[Test]
public Task VerifyImageFile()
{
    return VerifyFile("sample.jpg");
}
```
<sup><a href='/src/Tests/Samples.cs#L16-L24' title='Snippet source file'>snippet source</a> | <a href='#snippet-verifyimagefile' title='Start of snippet'>anchor</a></sup>
<a id='snippet-verifyimagefile-1'></a>
```cs
[Test]
public Task VerifyImageFileWithCustomEncoder()
{
    return VerifyFile("sample.jpg")
        .EncodeAsPng();
}
```
<sup><a href='/src/Tests/Samples.cs#L26-L35' title='Snippet source file'>snippet source</a> | <a href='#snippet-verifyimagefile-1' title='Start of snippet'>anchor</a></sup>
<!-- endSnippet -->

Two files are produced


#### Info file:

Samples.VerifyImageFile.00.verified.txt

<!-- snip2pet: Samples.VerifyImageFile.00.verified.txt -->
<a id='snippet-Samples.VerifyImageFile.00.verified.txt'></a>
```txt
{
  Width: 1599,
  Height: 1066,
  HorizontalResolution: 1.0,
  VerticalResolution: 1.0
}
```
<sup><a href='/src/Tests/Samples.VerifyImageFile.00.verified.txt#L1-L6' title='Snippet source file'>snippet source</a> | <a href='#snippet-Samples.VerifyImageFile.00.verified.txt' title='Start of snippet'>anchor</a></sup>
<!-- endSnippet -->


#### Image file:

Samples.VerifyImageFile.verified.jpg

<img src="/src/Tests/Samples.VerifyImageFile.01.verified.jpg" width="200px">


### Verify an Image

An instance if an `Image` can be verified using the following:

<!-- snippet: VerifyImage -->
<a id='snippet-verifyimage'></a>
```cs
[Test]
public Task VerifyImage()
{
    var image = new Image<Rgba32>(11, 11)
    {
        [5, 5] = Rgba32.ParseHex("#0000FF")
    };
    return Verify(image);
}
```
<sup><a href='/src/Tests/Samples.cs#L37-L49' title='Snippet source file'>snippet source</a> | <a href='#snippet-verifyimage' title='Start of snippet'>anchor</a></sup>
<!-- endSnippet -->


## File Samples

http://file-examples.com/



## Icon

[Swirl](https://thenounproject.com/term/pattern/2719636/) designed by [BÖCK, RU](https://thenounproject.com/titaniclast/) from [The Noun Project](https://thenounproject.com).
