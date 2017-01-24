---
title: "Version Information Editor | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.version.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Version Information editor, about Version Information editor"
  - "editors, Version Information"
  - "resource editors, Version Information editor"
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Version Information Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

バージョン情報は、製造元および製品の識別情報、製品のリリース番号、著作権と商標の通知で構成されます。 バージョン情報エディターでこのデータを作成および保守できます。これはバージョン情報リソースに保管されます。 バージョン情報リソースはアプリケーションに必須ではありませんが、アプリケーションの識別情報を収集するのに便利な場所です。 バージョン情報はセットアップ API でも使用されます。  
  
 バージョン情報リソースには、1 つの上位ブロックと 1 つ以上の下位ブロックがあります。つまり、固定された情報ブロックが上部に 1 つと、バージョン情報ブロックが下部に 1 つ以上 \(他の言語や文字セット用\) あります。 上部のブロックには、編集可能な数字のボックスと選択可能なドロップダウン リストの両方があります。 下位ブロックには、編集可能なテキスト ボックスだけがあります。  
  
> [!NOTE]
>  Windows 標準では、VS\_VERSION\_INFO という名前のバージョン リソースが 1 つだけあります。  
  
 バージョン情報エディターでは、次のことができます。  
  
-   [バージョン情報リソースの文字列の編集](../mfc/editing-a-string-in-a-version-information-resource.md)  
  
-   [別の言語のバージョン情報 \(新しいバージョン情報ブロック\) の追加](../mfc/adding-version-information-for-another-language.md)  
  
-   [バージョン情報ブロックの削除](../mfc/deleting-a-version-information-block.md)  
  
-   [プログラムからのバージョン情報へのアクセス](../mfc/accessing-version-information-from-within-your-program.md)  
  
    > [!NOTE]
    >  バージョン情報エディターの使用中は、多くの場合、右クリックするとショートカット メニューにリソース特有のコマンドが表示されます。 たとえば、ブロック ヘッダーのエントリをポイントしているときにクリックすると、ショートカット メニューに \[バージョン情報ブロックの新規作成\] コマンドと \[バージョン情報ブロックの削除\] コマンドが表示されます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
## 要件  
 Win32  
  
## 参照  
 [Resource Editors](../mfc/resource-editors.md)   
 [メニューとその他のリソース](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)