---
title: "方法: .NET Framework を使用して図形を描画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
ms.assetid: ffad5ae7-6ef4-4550-8940-be3f209a101d
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 62579ca21ba4a4dcf89aea6ff717ce6c884073b3
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-draw-shapes-with-the-net-framework"></a>方法: .NET Framework を使用して形状を描画する
次のコード例では、<xref:System.Drawing.Graphics>を変更するクラス、<xref:System.Windows.Forms.Form.OnPaint%2A>へのポインターを取得するイベント ハンドラー、<xref:System.Drawing.Graphics>メイン フォームのオブジェクト。 このポインターを使用して、フォームの背景色を設定し、行と円弧を使用して、描画、<xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName>と<xref:System.Drawing.Graphics.DrawArc%2A>メソッドです。  
  
> [!NOTE]
>  GDI + は Windows XP に付属し、Windows NT 4.0 SP 6、Windows 2000、Windows 98、および Windows me の再頒布可能として使用できます。 最新再頒布可能パッケージをダウンロードするを参照してください。 [http://go.microsoft.com/fwlink/p/?linkid=11232](http://go.microsoft.com/fwlink/p/?linkid=11232)です。 
  
## <a name="example"></a>例  
  
```  
#using <system.drawing.dll>  
using namespace System;  
using namespace System::Drawing;  
// ...  
protected:   
virtual Void Form1::OnPaint(PaintEventArgs^ pe ) override  
{  
   Graphics^ g = pe->Graphics;  
   g->Clear(Color::AntiqueWhite);  
  
   Rectangle rect = Form::ClientRectangle;  
   Rectangle smallRect;  
   smallRect.X = rect.X + rect.Width / 4;  
   smallRect.Y = rect.Y + rect.Height / 4;  
   smallRect.Width = rect.Width / 2;  
   smallRect.Height = rect.Height / 2;  
  
   Pen^ redPen = gcnew Pen(Color::Red);  
   redPen->Width = 4;  
   g->DrawLine(redPen, 0, 0, rect.Width, rect.Height);  
  
   Pen^ bluePen = gcnew Pen(Color::Blue);  
   bluePen->Width = 10;  
   g->DrawArc( bluePen, smallRect, 90, 270 );  
}  
```  
  
## <a name="see-also"></a>参照  
 [.NET プログラミング C + +/CLI (Visual C)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [System::Drawing 名前空間](https://msdn.microsoft.com/en-us/library/system.drawing.aspx)