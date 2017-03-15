---
title: "[IDL 属性] (プロパティの追加ウィザード) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.prop.idlattributes"
dev_langs: 
  - "C++"
ms.assetid: 356ed666-79d0-4bd9-a5e7-cda679cbadbd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# [IDL 属性] (プロパティの追加ウィザード)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロパティの追加ウィザードのこのページを使用して、プロパティのインターフェイス定義言語 \(IDL: Interface Definition Language\) を設定します。  
  
 **id**  
 プロパティを識別する数字の ID を設定します。  このオプションは、カスタム インターフェイスのプロパティに対しては使用できません。  「MIDL Language Reference」の「[id](http://msdn.microsoft.com/library/windows/desktop/aa367040)」を参照してください。  
  
 **helpcontext**  
 ユーザーがこのプロパティに関するヘルプ ファイルの情報を表示できるようにするためのコンテキスト ID を指定します。  「MIDL Language Reference」の「[helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851)」を参照してください。  
  
 **helpstring**  
 適用先の要素の記述に使用される文字列を指定します。  既定では、"プロパティ *Property name*" に設定されています。「MIDL Language Reference」の「[helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856)」を参照してください。  
  
## その他のオプション  
 すべてのプロパティ型に対してすべてのオプションを使用できるわけではありません。  
  
|オプション|Description|  
|-----------|-----------------|  
|**bindable**|プロパティがデータ連結をサポートすることを示します。  「MIDL Language Reference」の「[bindable](http://msdn.microsoft.com/library/windows/desktop/aa366738)」を参照してください。  プロパティのストック実装ではこのオプションが既定で設定されており、変更できません。|  
|**defaultbind**|この 1 つの連結可能なプロパティがオブジェクトを最もよく表すことを示します。  「MIDL Language Reference」の「[defaultbind](http://msdn.microsoft.com/library/windows/desktop/aa366790)」を参照してください。|  
|**displaybind**|このプロパティを連結可能としてユーザーに表示する必要があることを示します。  「MIDL Language Reference」の「[displaybind](http://msdn.microsoft.com/library/windows/desktop/aa366804)」を参照してください。|  
|**immediatebind**|データ連結オブジェクトのこのプロパティに対するすべての変更がすぐにデータベースに通知されることを示します。  「MIDL Language Reference」の「[immediatebind](http://msdn.microsoft.com/library/windows/desktop/aa367045)」を参照してください。|  
|**defaultcollelem**|プロパティが、既定のコレクションの要素に対するアクセサーであることを示します。  「MIDL Language Reference」の「[defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792)」を参照してください。|  
|**nonbrowsable**|プロパティ ブラウザーに表示しないインターフェイス メンバーまたはディスパッチ インターフェイス メンバーを指定します。  「MIDL Language Reference」の「[nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117)」を参照してください。|  
|**requestedit**|プロパティが **OnRequestEdit** 通知をサポートすることを示します。「MIDL Language Reference」の「[requestedit](http://msdn.microsoft.com/library/windows/desktop/aa367155)」を参照してください。  プロパティのストック実装ではこのオプションが既定で設定されており、変更できません。|  
|**source**|プロパティのメンバーがイベントのソースであることを示します。  「MIDL Language Reference」の「[source](http://msdn.microsoft.com/library/windows/desktop/aa367166)」を参照してください。|  
|**hidden**|プロパティが存在しても、ユーザー指向ブラウザーに表示されないことを示します。  「MIDL Language Reference」の「[hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861)」を参照してください。|  
|**restricted**|プロパティの任意の呼び出しができないことを示します。  「MIDL Language Reference」の「[restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157)」を参照してください。|  
|`local`|プロパティがリモートではないことを MIDL コンパイラに示します。  「MIDL Language Reference」の「[local](http://msdn.microsoft.com/library/windows/desktop/aa367071)」を参照してください。|  
  
## 参照  
 [プロパティの追加](../Topic/Adding%20a%20Property%20\(Visual%20C++\).md)   
 [\[名前\] \(プロパティの追加ウィザード\)](../Topic/Names,%20Add%20Property%20Wizard.md)   
 [インターフェイスの実装](../ide/implementing-an-interface-visual-cpp.md)   
 [ストック プロパティ](../ide/stock-properties.md)