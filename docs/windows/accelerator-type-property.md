---
title: "アクセラレータの [タイプ] プロパティ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Type プロパティ"
  - "VIRTKEY"
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# アクセラレータの [タイプ] プロパティ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アクセラレータの \[タイプ\] プロパティは、アクセラレータ ID に関連付けられているショートカット キーの組み合わせが、仮想キーの組み合わせであるか、または ASCII\/ANSI キー値であるかを決定します。  
  
-   \[タイプ\] プロパティが \[ASCII\] の場合、[&#91;修飾子&#93;](../windows/accelerator-modifier-property.md) は \[なし\] または \[Alt\] のいずれかです。または、キーの前に ^ を付けることによって、Ctrl キーを使用するアクセラレータを \[修飾子\] に指定することもできます。  
  
-   \[タイプ\] プロパティが \[VIRTKEY\] の場合は、\[修飾子\] の値と \[キー\] の値を任意に組み合わせることができます。  
  
    > [!NOTE]
    >  アクセラレータ テーブルに値を入力し、その値が ASCII\/ANSI として扱われるようにするには、テーブル内のエントリの \[タイプ\] をクリックし、ドロップダウン リストの \[ASCII\] を選択します。  ただし、\[編集\] メニューの \[キー タイピング登録\] を使用して \[キー\] プロパティを指定する場合は、\[キー\] のコードを入力する前に、\[タイプ\] プロパティを \[VIRTKEY\] から \[ASCII\] に変更する必要があります。  
  
## 要件  
 Win32  
  
## 参照  
 [Setting Accelerator Properties](../windows/setting-accelerator-properties.md)   
 [Accelerator Editor](../Topic/Accelerator%20Editor.md)