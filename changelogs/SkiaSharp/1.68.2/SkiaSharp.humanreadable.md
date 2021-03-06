# API diff: SkiaSharp.dll

## SkiaSharp.dll

### Namespace SkiaSharp

#### Type Changed: SkiaSharp.GRBackendTextureDesc

Added properties:

```csharp
public SKRectI Rect { get; }
public SKSizeI Size { get; }
```


#### Type Changed: SkiaSharp.GRGlBackendTextureDesc

Added properties:

```csharp
public SKRectI Rect { get; }
public SKSizeI Size { get; }
```


#### Type Changed: SkiaSharp.GRGlTextureInfo

Added constructor:

```csharp
public GRGlTextureInfo (uint target, uint id);
```


#### Type Changed: SkiaSharp.SKBitmap

Added methods:

```csharp
public static SKBitmap Decode (System.ReadOnlySpan<byte> buffer);
public static SKBitmap Decode (System.ReadOnlySpan<byte> buffer, SKImageInfo bitmapInfo);
public static SKImageInfo DecodeBounds (System.ReadOnlySpan<byte> buffer);
public SKData Encode (SKEncodedImageFormat format, int quality);
public bool Encode (System.IO.Stream dst, SKEncodedImageFormat format, int quality);
public SKBitmap Resize (SKSizeI size, SKFilterQuality quality);
public SKShader ToShader ();
public SKShader ToShader (SKShaderTileMode tmx, SKShaderTileMode tmy);
public SKShader ToShader (SKShaderTileMode tmx, SKShaderTileMode tmy, SKMatrix localMatrix);
```


#### Type Changed: SkiaSharp.SKCanvas

Added properties:

```csharp
public bool IsClipEmpty { get; }
public bool IsClipRect { get; }
```

Added methods:

```csharp
public void DrawArc (SKRect oval, float startAngle, float sweepAngle, bool useCenter, SKPaint paint);
public void DrawAtlas (SKImage atlas, SKRect[] sprites, SKRotationScaleMatrix[] transforms, SKPaint paint);
public void DrawAtlas (SKImage atlas, SKRect[] sprites, SKRotationScaleMatrix[] transforms, SKColor[] colors, SKBlendMode mode, SKPaint paint);
public void DrawAtlas (SKImage atlas, SKRect[] sprites, SKRotationScaleMatrix[] transforms, SKColor[] colors, SKBlendMode mode, SKRect cullRect, SKPaint paint);
public void DrawPatch (SKPoint[] cubics, SKColor[] colors, SKPoint[] texCoords, SKPaint paint);
public void DrawPatch (SKPoint[] cubics, SKColor[] colors, SKPoint[] texCoords, SKBlendMode mode, SKPaint paint);
public void DrawRoundRectDifference (SKRoundRect outer, SKRoundRect inner, SKPaint paint);
public int SaveLayer ();
```


#### Type Changed: SkiaSharp.SKColorSpacePrimaries

Added field:

```csharp
public static SKColorSpacePrimaries Empty;
```


#### Type Changed: SkiaSharp.SKColorSpaceTransferFn

Added field:

```csharp
public static SKColorSpaceTransferFn Empty;
```


#### Type Changed: SkiaSharp.SKDynamicMemoryWStream

Added methods:

```csharp
public bool CopyTo (System.IO.Stream dst);
public void CopyTo (System.Span<byte> data);
```


#### Type Changed: SkiaSharp.SKFontManager

Added method:

```csharp
public SKTypeface MatchFamily (string familyName);
```


#### Type Changed: SkiaSharp.SKImage

Obsoleted methods:

```diff
 [Obsolete ("Use FromPixels (SKImageInfo, SKData, int) instead.")]
 public static SKImage FromPixelData (SKImageInfo info, SKData data, int rowBytes);
```

Added methods:

```csharp
public static SKImage FromPixels (SKImageInfo info, SKData data);
public bool IsValid (GRContext context);
public bool ReadPixels (SKPixmap pixmap);
public bool ReadPixels (SKImageInfo dstInfo, IntPtr dstPixels);
public bool ReadPixels (SKImageInfo dstInfo, IntPtr dstPixels, int dstRowBytes);
public SKImage ToRasterImage (bool ensurePixelData);
public SKShader ToShader ();
public SKImage ToTextureImage (GRContext context);
public SKImage ToTextureImage (GRContext context, SKColorSpace colorspace);
```


#### Type Changed: SkiaSharp.SKImageInfo

Added methods:

```csharp
public SKImageInfo WithSize (SKSizeI size);
```


#### Type Changed: SkiaSharp.SKMask

Added methods:

```csharp
public static SKMask Create (System.ReadOnlySpan<byte> image, SKRectI bounds, uint rowBytes, SKMaskFormat format);
public System.Span<byte> GetImageSpan ();
```


#### Type Changed: SkiaSharp.SKMatrix

Added constructor:

```csharp
public SKMatrix (float[] values);
```

Added fields:

```csharp
public static SKMatrix Empty;
public static SKMatrix Identity;
```

Added properties:

```csharp
public bool IsIdentity { get; }
public bool IsInvertible { get; }
```

Obsoleted methods:

```diff
 [Obsolete ("Use MapRect(SKRect) instead.")]
 public static void MapRect (ref SKMatrix matrix, out SKRect dest, ref SKRect source);
 [Obsolete ("Use PostConcat(SKMatrix) instead.")]
 public static void PostConcat (ref SKMatrix target, SKMatrix matrix);
 [Obsolete ("Use PostConcat(SKMatrix) instead.")]
 public static void PostConcat (ref SKMatrix target, ref SKMatrix matrix);
 [Obsolete ("Use PreConcat(SKMatrix) instead.")]
 public static void PreConcat (ref SKMatrix target, SKMatrix matrix);
 [Obsolete ("Use PreConcat(SKMatrix) instead.")]
 public static void PreConcat (ref SKMatrix target, ref SKMatrix matrix);
 [Obsolete ("Use CreateRotation(float) instead.")]
 public static void Rotate (ref SKMatrix matrix, float radians);
 [Obsolete ("Use CreateRotation(float, float, float) instead.")]
 public static void Rotate (ref SKMatrix matrix, float radians, float pivotx, float pivoty);
 [Obsolete ("Use CreateRotationDegrees(float) instead.")]
 public static void RotateDegrees (ref SKMatrix matrix, float degrees);
 [Obsolete ("Use CreateRotationDegrees(float, float, float) instead.")]
 public static void RotateDegrees (ref SKMatrix matrix, float degrees, float pivotx, float pivoty);
 [Obsolete ()]
 public void SetScaleTranslate (float sx, float sy, float tx, float ty);
```

Added methods:

```csharp
public static SKMatrix Concat (SKMatrix first, SKMatrix second);
public static SKMatrix CreateIdentity ();
public static SKMatrix CreateRotation (float radians);
public static SKMatrix CreateRotation (float radians, float pivotX, float pivotY);
public static SKMatrix CreateRotationDegrees (float degrees);
public static SKMatrix CreateRotationDegrees (float degrees, float pivotX, float pivotY);
public static SKMatrix CreateScale (float x, float y);
public static SKMatrix CreateScale (float x, float y, float pivotX, float pivotY);
public static SKMatrix CreateSkew (float x, float y);
public static SKMatrix CreateTranslation (float x, float y);
public SKMatrix Invert ();
public SKPoint MapVector (SKPoint vector);
public SKMatrix PostConcat (SKMatrix matrix);
public SKMatrix PreConcat (SKMatrix matrix);
```


#### Type Changed: SkiaSharp.SKMatrix44

Added property:

```csharp
public bool IsInvertible { get; }
```

Added methods:

```csharp
public static SKMatrix44 CreateTranslation (float x, float y, float z);
public void Set3x3ColumnMajor (float[] src);
public void Set3x3RowMajor (float[] src);
public static SKMatrix44 op_Implicit (SKMatrix matrix);
```


#### Type Changed: SkiaSharp.SKPath

Added method:

```csharp
public void Transform (SKMatrix matrix, SKPath destination);
```


#### Type Changed: SkiaSharp.SKPathMeasure

Added methods:

```csharp
public SKMatrix GetMatrix (float distance, SKPathMeasureMatrixFlags flags);
public SKPoint GetPosition (float distance);
public SKPath GetSegment (float start, float stop, bool startWithMoveTo);
public SKPoint GetTangent (float distance);
public void SetPath (SKPath path);
```


#### Type Changed: SkiaSharp.SKPicture

Added methods:

```csharp
public SKShader ToShader ();
public SKShader ToShader (SKShaderTileMode tmx, SKShaderTileMode tmy);
public SKShader ToShader (SKShaderTileMode tmx, SKShaderTileMode tmy, SKRect tile);
public SKShader ToShader (SKShaderTileMode tmx, SKShaderTileMode tmy, SKMatrix localMatrix, SKRect tile);
```


#### Type Changed: SkiaSharp.SKPixmap

Obsoleted methods:

```diff
 [Obsolete ("Use Encode(SKWStream, SKJpegEncoderOptions) instead.")]
 public static bool Encode (SKWStream dst, SKPixmap src, SKJpegEncoderOptions options);
 [Obsolete ("Use Encode(SKWStream, SKPngEncoderOptions) instead.")]
 public static bool Encode (SKWStream dst, SKPixmap src, SKPngEncoderOptions options);
 [Obsolete ("Use Encode(SKWStream, SKWebpEncoderOptions) instead.")]
 public static bool Encode (SKWStream dst, SKPixmap src, SKWebpEncoderOptions options);
 [Obsolete ("Use Encode(SKWStream, SKEncodedImageFormat, int) instead.")]
 public static bool Encode (SKWStream dst, SKBitmap src, SKEncodedImageFormat format, int quality);
 [Obsolete ("Use Encode(SKWStream, SKEncodedImageFormat, int) instead.")]
 public static bool Encode (SKWStream dst, SKPixmap src, SKEncodedImageFormat encoder, int quality);
```

Added methods:

```csharp
public bool Encode (System.IO.Stream dst, SKJpegEncoderOptions options);
public bool Encode (System.IO.Stream dst, SKPngEncoderOptions options);
public bool Encode (System.IO.Stream dst, SKWebpEncoderOptions options);
public bool Encode (System.IO.Stream dst, SKEncodedImageFormat encoder, int quality);
public bool Erase (SKColorF color);
public bool Erase (SKColorF color, SKRectI subset);
public System.Span<T> GetPixelSpan<T> ();
```


#### Type Changed: SkiaSharp.SKRegion

Added properties:

```csharp
public bool IsComplex { get; }
public bool IsEmpty { get; }
public bool IsRect { get; }
```

Added methods:

```csharp
public bool Contains (SKPath path);
public bool Contains (SKRectI rect);
public SKRegion.ClipIterator CreateClipIterator (SKRectI clip);
public SKRegion.RectIterator CreateRectIterator ();
public SKRegion.SpanIterator CreateSpanIterator (int y, int left, int right);
public SKPath GetBoundaryPath ();
public bool QuickContains (SKRectI rect);
public bool QuickReject (SKPath path);
public bool QuickReject (SKRectI rect);
public bool QuickReject (SKRegion region);
public void SetEmpty ();
public bool SetRects (SKRectI[] rects);
public void Translate (int x, int y);
```


#### Type Changed: SkiaSharp.SKRoundRect

Added constructor:

```csharp
public SKRoundRect (SKRect rect, float radius);
```


#### Type Changed: SkiaSharp.SKShader

Added methods:

```csharp
public static SKShader CreateBitmap (SKBitmap src);
public static SKShader CreateColor (SKColorF color, SKColorSpace colorspace);
public static SKShader CreateImage (SKImage src);
public static SKShader CreateImage (SKImage src, SKShaderTileMode tmx, SKShaderTileMode tmy);
public static SKShader CreateImage (SKImage src, SKShaderTileMode tmx, SKShaderTileMode tmy, SKMatrix localMatrix);
public static SKShader CreateLinearGradient (SKPoint start, SKPoint end, SKColorF[] colors, SKColorSpace colorspace, SKShaderTileMode mode);
public static SKShader CreateLinearGradient (SKPoint start, SKPoint end, SKColorF[] colors, SKColorSpace colorspace, float[] colorPos, SKShaderTileMode mode);
public static SKShader CreateLinearGradient (SKPoint start, SKPoint end, SKColorF[] colors, SKColorSpace colorspace, float[] colorPos, SKShaderTileMode mode, SKMatrix localMatrix);
public static SKShader CreatePerlinNoiseFractalNoise (float baseFrequencyX, float baseFrequencyY, int numOctaves, float seed, SKSizeI tileSize);
public static SKShader CreatePerlinNoiseImprovedNoise (float baseFrequencyX, float baseFrequencyY, int numOctaves, float z);
public static SKShader CreatePerlinNoiseTurbulence (float baseFrequencyX, float baseFrequencyY, int numOctaves, float seed, SKSizeI tileSize);
public static SKShader CreatePicture (SKPicture src);
public static SKShader CreateRadialGradient (SKPoint center, float radius, SKColorF[] colors, SKColorSpace colorspace, SKShaderTileMode mode);
public static SKShader CreateRadialGradient (SKPoint center, float radius, SKColorF[] colors, SKColorSpace colorspace, float[] colorPos, SKShaderTileMode mode);
public static SKShader CreateRadialGradient (SKPoint center, float radius, SKColorF[] colors, SKColorSpace colorspace, float[] colorPos, SKShaderTileMode mode, SKMatrix localMatrix);
public static SKShader CreateSweepGradient (SKPoint center, SKColorF[] colors, SKColorSpace colorspace);
public static SKShader CreateSweepGradient (SKPoint center, SKColorF[] colors, SKColorSpace colorspace, float[] colorPos);
public static SKShader CreateSweepGradient (SKPoint center, SKColorF[] colors, SKColorSpace colorspace, float[] colorPos, SKMatrix localMatrix);
public static SKShader CreateSweepGradient (SKPoint center, SKColorF[] colors, SKColorSpace colorspace, SKShaderTileMode tileMode, float startAngle, float endAngle);
public static SKShader CreateSweepGradient (SKPoint center, SKColorF[] colors, SKColorSpace colorspace, float[] colorPos, SKShaderTileMode tileMode, float startAngle, float endAngle);
public static SKShader CreateSweepGradient (SKPoint center, SKColorF[] colors, SKColorSpace colorspace, float[] colorPos, SKShaderTileMode tileMode, float startAngle, float endAngle, SKMatrix localMatrix);
public static SKShader CreateTwoPointConicalGradient (SKPoint start, float startRadius, SKPoint end, float endRadius, SKColorF[] colors, SKColorSpace colorspace, SKShaderTileMode mode);
public static SKShader CreateTwoPointConicalGradient (SKPoint start, float startRadius, SKPoint end, float endRadius, SKColorF[] colors, SKColorSpace colorspace, float[] colorPos, SKShaderTileMode mode);
public static SKShader CreateTwoPointConicalGradient (SKPoint start, float startRadius, SKPoint end, float endRadius, SKColorF[] colors, SKColorSpace colorspace, float[] colorPos, SKShaderTileMode mode, SKMatrix localMatrix);
public SKShader WithColorFilter (SKColorFilter filter);
public SKShader WithLocalMatrix (SKMatrix localMatrix);
```


#### Type Changed: SkiaSharp.SKSvgCanvas

Obsoleted methods:

```diff
 [Obsolete ("Use Create(SKRect, Stream) instead.")]
 public static SKCanvas Create (SKRect bounds, SKXmlWriter writer);
```

Added methods:

```csharp
public static SKCanvas Create (SKRect bounds, SKWStream stream);
public static SKCanvas Create (SKRect bounds, System.IO.Stream stream);
```


#### Type Changed: SkiaSharp.SKSwizzle

Added method:

```csharp
public static void SwapRedBlue (System.Span<byte> pixels);
```


#### Type Changed: SkiaSharp.SKTypeface

Added property:

```csharp
public int GlyphCount { get; }
```

Obsoleted methods:

```diff
 [Obsolete ("Use CountGlyphs(byte[], SKTextEncoding) instead.")]
 public int CountGlyphs (byte[] str, SKEncoding encoding);
 [Obsolete ("Use CountGlyphs(ReadOnlySpan<byte>, SKTextEncoding) instead.")]
 public int CountGlyphs (System.ReadOnlySpan<byte> str, SKEncoding encoding);
 [Obsolete ("Use CountGlyphs(string) instead.")]
 public int CountGlyphs (string str, SKEncoding encoding);
 [Obsolete ("Use CountGlyphs(ReadOnlySpan<byte>, SKTextEncoding) instead.")]
 public int CountGlyphs (IntPtr str, int strLen, SKEncoding encoding);
 [Obsolete ("Use GetGlyphs(ReadOnlySpan<byte>, SKTextEncoding) instead.")]
 public ushort[] GetGlyphs (byte[] text, SKEncoding encoding);
 [Obsolete ("Use GetGlyphs(ReadOnlySpan<byte>, SKTextEncoding) instead.")]
 public ushort[] GetGlyphs (System.ReadOnlySpan<byte> text, SKEncoding encoding);
 [Obsolete ("Use GetGlyphs(string) instead.")]
 public ushort[] GetGlyphs (string text, SKEncoding encoding);
 [Obsolete ("Use GetGlyphs(string) instead.")]
 public int GetGlyphs (string text, out ushort[] glyphs);
 [Obsolete ("Use GetGlyphs(byte[], SKTextEncoding) instead.")]
 public int GetGlyphs (byte[] text, SKEncoding encoding, out ushort[] glyphs);
 [Obsolete ("Use GetGlyphs(IntPtr, int, SKTextEncoding) instead.")]
 public ushort[] GetGlyphs (IntPtr text, int length, SKEncoding encoding);
 [Obsolete ("Use GetGlyphs(ReadOnlySpan<byte>, SKTextEncoding) instead.")]
 public int GetGlyphs (System.ReadOnlySpan<byte> text, SKEncoding encoding, out ushort[] glyphs);
 [Obsolete ("Use GetGlyphs(string) instead.")]
 public int GetGlyphs (string text, SKEncoding encoding, out ushort[] glyphs);
 [Obsolete ("Use GetGlyphs(IntPtr, int, SKTextEncoding) instead.")]
 public int GetGlyphs (IntPtr text, int length, SKEncoding encoding, out ushort[] glyphs);
```

Added methods:

```csharp
public bool ContainsGlyphs (System.ReadOnlySpan<char> text);
public bool ContainsGlyphs (string text);
public bool ContainsGlyphs (System.ReadOnlySpan<byte> text, SKTextEncoding encoding);
public bool ContainsGlyphs (IntPtr text, int length, SKTextEncoding encoding);
public int CountGlyphs (System.ReadOnlySpan<char> str);
public int CountGlyphs (byte[] str, SKTextEncoding encoding);
public int CountGlyphs (System.ReadOnlySpan<byte> str, SKTextEncoding encoding);
public int CountGlyphs (IntPtr str, int strLen, SKTextEncoding encoding);
public ushort[] GetGlyphs (System.ReadOnlySpan<char> text);
public ushort[] GetGlyphs (System.ReadOnlySpan<byte> text, SKTextEncoding encoding);
public ushort[] GetGlyphs (IntPtr text, int length, SKTextEncoding encoding);
public int[] GetKerningPairAdjustments (System.ReadOnlySpan<ushort> glyphs);
```


#### Type Changed: SkiaSharp.SkiaExtensions

Added methods:

```csharp
public static SKAlphaType GetAlphaType (this SKColorType colorType, SKAlphaType alphaType);
public static int GetBytesPerPixel (this SKColorType colorType);
public static SKTextEncoding ToTextEncoding (this SKEncoding encoding);
```


#### Type Changed: SkiaSharp.StringUtilities

Obsoleted methods:

```diff
 [Obsolete ("Use GetEncodedText(string, SKTextEncoding) instead.")]
 public static byte[] GetEncodedText (string text, SKEncoding encoding);
```

Added methods:

```csharp
public static byte[] GetEncodedText (System.ReadOnlySpan<char> text, SKTextEncoding encoding);
public static string GetString (System.ReadOnlySpan<byte> data, SKTextEncoding encoding);
public static string GetString (System.ReadOnlySpan<byte> data, int index, int count, SKTextEncoding encoding);
```


#### New Type: SkiaSharp.SKColorF

```csharp
public struct SKColorF {
	// constructors
	public SKColorF (float red, float green, float blue);
	public SKColorF (float red, float green, float blue, float alpha);
	// fields
	public static SKColorF Empty;
	// properties
	public float Alpha { get; }
	public float Blue { get; }
	public float Green { get; }
	public float Hue { get; }
	public float Red { get; }
	// methods
	public SKColorF Clamp ();
	public static SKColorF FromHsl (float h, float s, float l, float a);
	public static SKColorF FromHsv (float h, float s, float v, float a);
	public void ToHsl (out float h, out float s, out float l);
	public void ToHsv (out float h, out float s, out float v);
	public SKColorF WithAlpha (float alpha);
	public SKColorF WithBlue (float blue);
	public SKColorF WithGreen (float green);
	public SKColorF WithRed (float red);
	public static SKColor op_Explicit (SKColorF color);
	public static SKColorF op_Implicit (SKColor color);
}
```

#### New Type: SkiaSharp.SKRotationScaleMatrix

```csharp
public struct SKRotationScaleMatrix {
	// constructors
	public SKRotationScaleMatrix (float scos, float ssin, float tx, float ty);
	// fields
	public static SKRotationScaleMatrix Empty;
	public static SKRotationScaleMatrix Identity;
	// properties
	public float SCos { get; set; }
	public float SSin { get; set; }
	public float TX { get; set; }
	public float TY { get; set; }
	// methods
	public static SKRotationScaleMatrix Create (float scale, float radians, float tx, float ty, float anchorX, float anchorY);
	public static SKRotationScaleMatrix CreateDegrees (float scale, float degrees, float tx, float ty, float anchorX, float anchorY);
	public static SKRotationScaleMatrix CreateIdentity ();
	public static SKRotationScaleMatrix CreateRotation (float radians, float anchorX, float anchorY);
	public static SKRotationScaleMatrix CreateRotationDegrees (float degrees, float anchorX, float anchorY);
	public static SKRotationScaleMatrix CreateScale (float s);
	public static SKRotationScaleMatrix CreateTranslation (float x, float y);
	public SKMatrix ToMatrix ();
}
```


