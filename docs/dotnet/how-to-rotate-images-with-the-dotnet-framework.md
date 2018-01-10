---
title: "方法: .NET Framework でのイメージを回転 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+ [C++], rotating images
- graphics [C++], rotating images
ms.assetid: e32104d5-87d0-47a9-a22f-9bc835b7e8d7
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 387bd9733ad591f45ef206be8856d4dd4edd464d
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-rotate-images-with-the-net-framework"></a>方法: .NET Framework を使用してイメージを回転する
使用を次のコード例に示します、<xref:System.Drawing.Image?displayProperty=fullName>クラスをディスクからイメージを読み込んで、90 度回転、および新しい .jpg ファイルとして保存します。  
  
> [!NOTE]
>  GDI + は Windows XP に付属しは Windows NT 4.0 SP 6、Windows 2000、Windows 98、および Windows Me の再頒布可能として使用できます。 最新再頒布可能パッケージをダウンロードするを参照してください。 [http://go.microsoft.com/fwlink/p/?linkid=11232](http://go.microsoft.com/fwlink/p/?linkid=11232)です。 
  
## <a name="example"></a>例  
  
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
  
## <a name="see-also"></a>参照  
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)