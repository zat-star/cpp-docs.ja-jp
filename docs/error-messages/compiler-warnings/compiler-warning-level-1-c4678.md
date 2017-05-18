---
title: "コンパイラの警告 (レベル 1) C4678 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4678
dev_langs:
- C++
helpviewer_keywords:
- C4678
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: d35e60d60d194bc0ca68a116dc45b6d9864d9fe2
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4678"></a>コンパイラの警告 (レベル 1) C4678
基底クラス 'base_type' のアクセス可能性が 'derived_type' よりも小さいです。  
  
パブリック型は、プライベート型から派生します。 参照されたアセンブリでパブリック型がインスタンス化される場合は、プライベート基本型のメンバーにアクセスできません。  
  
C4678 は古いコンパイラ オプションを使用して到達のみ**/clr:oldSyntax**します。 使用する場合はエラー **/clr**、あまりアクセス可能な基本クラスをその派生クラスです。  

