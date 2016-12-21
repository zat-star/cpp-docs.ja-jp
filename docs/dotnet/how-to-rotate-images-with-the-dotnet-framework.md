---
title: "方法: .NET Framework を使用してイメージを回転する | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GDI+ [C++], 回転 (イメージを)"
  - "グラフィックス [C++], 回転 (イメージを)"
ms.assetid: e32104d5-87d0-47a9-a22f-9bc835b7e8d7
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: .NET Framework を使用してイメージを回転する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

<xref:System.Drawing.Image?displayProperty=fullName> クラスを使用して、ディスクからイメージを読み込み、そのイメージを 90 度回転してから、新しい .jpg ファイルに保存する方法を次のコード例に示します。  
  
> [!NOTE]
>  GDI\+ は Windows XP に含まれており、Windows NT 4.0 SP6、Windows 2000、Windows 98、および Windows Me \(Millennium Edition\) については再頒布可能パッケージとして入手できます。  最新の再頒布可能をダウンロードするには、参照してください [http:\/\/go.microsoft.com\/fwlink\/?linkid\=11232](http://go.microsoft.com/fwlink/?linkid=11232)。  詳細については、「[GDI\+](_gdiplus_GDI_start_cpp)」を参照してください。  
  
## 使用例  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
  
int main()  
{  
   Image^ image = Image::FromFile("SampleImage.jpg");  
   image->RotateFlip( RotateFlipType::Rotate90FlipNone );  
   image->Save("SampleImage_rotated.jpg");  
   return 0;  
}  
```  
  
## 参照  
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)