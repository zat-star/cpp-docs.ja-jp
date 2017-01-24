---
title: "方法: .NET Framework を使用してイメージを表示する | Microsoft Docs"
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
  - "GDI+ [C++], 表示 (イメージを)"
  - "グラフィックス [C++], 表示 (イメージを)"
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: .NET Framework を使用してイメージを表示する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OnPaint イベント ハンドラーを修正して、メイン フォームの <xref:System.Drawing.Graphics> オブジェクトへのポインターを取得する方法を次のコード例に示します。  一般に Visual Studio アプリケーション ウィザードを使って作成される Windows フォーム アプリケーションでは、<xref:System.Windows.Forms.Form.OnPaint%2A> 関数が使用されます。  
  
 イメージは、<xref:System.Drawing.Image> クラスによって表されます。  イメージのデータは、<xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> メソッドを使用して .jpg ファイルから読み込まれます。  イメージがフォームに描画される前に、フォームのサイズがイメージに合わせて変更されます。  <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> メソッドを使用してイメージが描画されます。  
  
 <xref:System.Drawing.Graphics> クラスおよび <xref:System.Drawing.Image> クラスは、共に <xref:System.Drawing?displayProperty=fullName> 名前空間にあります。  
  
> [!NOTE]
>  GDI\+ は Windows XP に含まれており、Windows NT 4.0 SP6、Windows 2000、Windows 98、および Windows Me では再頒布可能パッケージとして入手できます。  最新の再頒布可能をダウンロードするには、参照してください [http:\/\/go.microsoft.com\/fwlink\/?linkid\=11232](http://go.microsoft.com/fwlink/?linkid=11232)。  詳細については、[GDI\+](_gdiplus_GDI_start_cpp) の GDI\+ SDK の説明を参照してください。  
  
## 使用例  
  
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
  
## 参照  
 <xref:System.Drawing?displayProperty=fullName>   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)