---
title: "方法: .NET Framework でのイメージ ファイル形式に変換 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: 5d5384b0-b9b7-4262-b9ad-c4cb95f75ee4
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eff94d00f92fe0a52162c986662209168974e072
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-convert-image-file-formats-with-the-net-framework"></a>方法: .NET Framework を使用してイメージ ファイル形式を変換する
次のコード例を示しています、<xref:System.Drawing.Image?displayProperty=fullName>クラスおよび<xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName>列挙型に変換し、イメージ ファイルを保存するために使用します。 次のコードは、.jpg ファイルからイメージを読み込み、.gif、.bmp の両方のファイル形式で保存されます。  
  
> [!NOTE]
>  GDI + は Windows XP、Windows Server 2003、および Windows Vista に付属しは Windows 2000 の再頒布可能として使用できます。 最新再頒布可能パッケージをダウンロードするを参照してください。 [http://go.microsoft.com/fwlink/?linkid=11232](http://go.microsoft.com/fwlink/?linkid=11232)です。   
  
## <a name="example"></a>例  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
using namespace System::Drawing::Imaging;  
  
int main()  
{  
   Image^ image = Image::FromFile("SampleImage.jpg");  
   image->Save("SampleImage.png", ImageFormat::Png);  
   image->Save("SampleImage.bmp", ImageFormat::Bmp);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Drawing>   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)