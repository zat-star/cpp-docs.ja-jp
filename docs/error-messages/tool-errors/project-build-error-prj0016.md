---
title: "プロジェクト ビルド エラー PRJ0016 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0016"
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# プロジェクト ビルド エラー PRJ0016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このユーザーのセキュリティ設定が原因で、プロセスを作成できません。これらの設定はビルドで必要です。  
  
 1 つのプロセスを使用して複数のプロセスを作成できる権限を持たないユーザーとして、ログインしています。  このユーザー アカウントのアクセス許可レベルを変更するか、アカウント管理者に連絡してください。  
  
 このエラーは、次のレジストリ キーが設定されている場合にも発生することがあります。  
  
 \\\\HKCU\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer\\RestrictRun  
  
 このエラーを解決するには、RestrictRun キーを削除します。  このレジストリ キーが必要な場合は、キーのエントリの一覧に "vcspawn.exe" を追加します。  
  
 また、このエラーのほかの原因としては、ポリシー設定で、レジストリ キー HKEY\_CURRENT\_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\RestrictRun の下に、このユーザー アカウントに許可される Windows プログラムとして VCSpawn.exe が含まれていない場合があります。  
  
 詳細については、以下のトピックを参照してください。  
  
-   使用可能なオンのサポート技術情報の文書 324153 [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153)。  
  
-   「[Adhering to System Policy Settings](http://msdn.microsoft.com/library/aa372139)」の「Run only allowed Windows applications」。