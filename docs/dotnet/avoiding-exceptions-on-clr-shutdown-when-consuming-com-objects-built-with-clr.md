---
title: "Clr で構築された COM オブジェクトによってスローされた例外の回避 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 287c9831f8c604272b37ac85528d66fe640de557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>/clr で構築された COM オブジェクト使用時における CLR シャットダウンの例外の回避
共通言語ランタイム (CLR) がシャット ダウン モードになると、ネイティブ関数には CLR サービスへのアクセスが制限されます。 COM オブジェクトをコンパイルしたに対して Release を呼び出すしようとするとき**/clr**、ネイティブ コードに遷移する CLR および iunknown::release 呼び出し (これは、マネージ コードで定義されている) に対応するマネージ コードに遷移の戻さです。 CLR では、シャット ダウン モードであるために、マネージ コードへのコールバックができなくなります。  
  
 これを解決するには、リリースのメソッドから呼び出すデストラクターがネイティブ コードのみを含めることを確認します。  
  
## <a name="see-also"></a>参照  
 [混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)