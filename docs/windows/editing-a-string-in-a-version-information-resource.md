---
title: "Editing a String in a Version Information Resource | Microsoft Docs"
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
  - "vc.editors.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "version information resources"
  - "resources [Visual Studio], editing version information"
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Editing a String in a Version Information Resource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### バージョン情報リソースの文字列を編集するには  
  
1.  1 回アイテムをクリックして選択し、もう一度クリックして編集を開始します。 バージョン情報テーブルで直接、または [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)で変更を加えます。 加えた変更は、両方の場所で反映されます。  
  
     **メモ** バージョン情報エディターで **FILEFLAGS** キーを編集するとき、.rc ファイルの **デバッグ**、**プライベート ビルド**、または **特殊ビルド** プロパティは設定できません \(\[プロパティ\] ウィンドウ\)。  
  
    -   バージョン情報エディターは、**\_DEBUG** ビルド フラグに基づいて、リソース スクリプトの \#ifdef で **デバッグ** プロパティを設定します。  
  
    -   **プライベート ビルド** キーの**値**がバージョン情報テーブルに設定されている場合、**FILEFLAGS** キーに対応する **プライベート ビルド** プロパティ \(\[プロパティ\] ウィンドウ\) は **True** になります。**値**が空の場合、プロパティは **False** になります。 同様に、**特殊ビルド** キー \(バージョン情報テーブル内\) は、**FILEFLAGS** キーの **特殊ビルド**{b\> \<b}プロパティと関連付けられます。  
  
 キーまたは値の列見出しをクリックすることにより、文字列ブロックの情報シーケンスをソートすることができます。 これらの見出しは、選択した順序に情報を自動的に再配置します。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
 **要件**  
  
 Win32  
  
## 参照  
 [Version Information Editor](../mfc/version-information-editor.md)   
 [バージョン情報 \(Windows\)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)