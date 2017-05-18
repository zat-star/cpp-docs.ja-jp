---
title: "リンカー ツールの警告 LNK4105 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4105
dev_langs:
- C++
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f7d0a4e956ec78dfdac7f54895405025bdb11559
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4105"></a>リンカー ツールの警告 LNK4105
引数がオプション 'option'; で指定されていません。オプションを無視します。  
  
 この警告は発生時に、 [/LIBPATH](../../build/reference/libpath-additional-libpath.md)オプションを設定します。 このオプションを使用してディレクトリが指定されていない場合、リンカーはオプションが無視され、この警告メッセージが生成されます。  
  
 既存の環境のライブラリの設定をオーバーライドする必要はありません、リンカーのコマンドラインから/LIBPATH オプションを削除します。 ライブラリの別の検索パスを使用する場合は、/LIBPATH オプションに続く代替パスを指定します。  
  
## <a name="example"></a>例  
  
```  
link /libpath:c:\filepath\lib bar.obj  
```  
  
 転送に必要なライブラリを検索するリンカー`c:\filepath\lib`既定の場所で検索する前にします。
