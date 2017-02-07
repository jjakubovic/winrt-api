---
-api-type: winrt property
---
 To access the pixel content from C# or Microsoft Visual Basic, you can use the **AsStream** extension method to access the underlying buffer as a stream.
 To access the pixel content from C++, you can query for the **IBufferByteAccess** type (defined in Robuffer.h) and directly access its **Buffer** property.