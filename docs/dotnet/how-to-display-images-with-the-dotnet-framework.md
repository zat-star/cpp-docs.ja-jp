---
title: "方法: .NET Framework でのイメージを表示 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+ [C++], displaying images
- graphics [C++], displaying images
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7c12d6a67f6fbe73802d3b876621a2ea606af553
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-display-images-with-the-net-framework"></a>方法: .NET Framework を使用してイメージを表示する
次のコード例へのポインターを取得する OnPaint イベント ハンドラーを変更する、<xref:System.Drawing.Graphics>メイン フォームのオブジェクト。 <xref:System.Windows.Forms.Form.OnPaint%2A>関数が Visual Studio のアプリケーション ウィザードで作成されたほとんどの場合、Windows フォーム アプリケーションの目的としています。  
  
 イメージがによって表される、<xref:System.Drawing.Image>クラスです。 使用して .jpg ファイルから画像データが読み込まれた、<xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName>メソッドです。 イメージがフォームに描画されると、前に、画像に合わせて、フォームがサイズ変更されます。 イメージの描画を実行、<xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName>メソッドです。  
  
 <xref:System.Drawing.Graphics>と<xref:System.Drawing.Image>クラスはどちらも、<xref:System.Drawing?displayProperty=fullName>名前空間。  
  
> [!NOTE]
>  GDI + は Windows XP に付属し、Windows NT 4.0 SP 6、Windows 2000、Windows 98、および Windows me の再頒布可能として使用できます。 最新再頒布可能パッケージをダウンロードするを参照してください。 [http://go.microsoft.com/fwlink/p/?linkid=11232](http://go.microsoft.com/fwlink/p/?linkid=11232)です。   
  
## <a name="example"></a>例  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
  
protected:  
virtual Void Form1::OnPaint(PaintEventArgs^ pe) override  
{  
    Graphics^ g = pe->Graphics;  
    Image^ image = Image::FromFile("SampleImage.jpg");  
    Form::ClientSize = image->Size;  
    g->DrawImage( image, 0, 0, image->Size.Width, image->Size.Height );  
}  
```  
  
## <a name="see-also"></a>参照  
 <xref:System.Drawing?displayProperty=fullName>   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)