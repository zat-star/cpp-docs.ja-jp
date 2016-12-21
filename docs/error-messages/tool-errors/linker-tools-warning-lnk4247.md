---
title: "リンカー ツールの警告 LNK4247 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4247"
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エントリ ポイント 'decorated\_function\_name' にはスレッド属性が既に指定されています。'属性' は無視されます。  
  
 [\/ENTRY \(エントリ ポイント シンボル\)](../../build/reference/entry-entry-point-symbol.md) で指定されたエントリ ポイントにスレッド処理属性がありましたが、[\/CLRTHREADATTRIBUTE \(CLR スレッド属性の設定\)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) は別のスレッド処理モデルでも指定されていました。  
  
 リンカーは \/CLRTHREADATTRIBUTE で指定された値を無視しました。  
  
 この警告を解決するには、次の方法があります。  
  
-   \/CLRTHREADATTRIBUTE をビルドから削除します。  
  
-   属性をソース コード ファイルから削除します。  
  
-   属性をソースから削除し、かつ \/CLRTHREADATTRIBUTE をビルドから削除して、既定の CLR スレッド処理モデルを受け入れます。  
  
-   ソースの属性に一致するように \/CLRTHREADATTRIBUTE に渡される値を変更します。  
  
-   \/CLRTHREADATTRIBUTE に渡される値に一致するようにソースの属性を変更します。  
  
 次のサンプルは LNK4247 を生成します。  
  
```  
// LNK4247.cpp  
// compile with: /clr /c  
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console  
 [System::MTAThreadAttribute]  
void functionTitle (){}  
```