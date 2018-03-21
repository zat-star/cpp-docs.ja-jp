---
title: "PogoSafeMode |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- PogoSafeMode
ms.assetid: 2daeeff7-44cb-417f-90eb-6b9edf658533
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5f40dad6feff9e49deeb495e8acbf2584dea3e41
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="pogosafemode"></a>PogoSafeMode
アプリケーションのプロファイリングに高速モードとセーフ モードのどちらを使用するかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
PogoSafeMode  
```  
  
## <a name="remarks"></a>コメント  
 ガイド付き最適化のプロファイル (PGO: Profile-Guided Optimization) では、プロファイリング フェーズで高速モードとセーフ モードの 2 つのモードを使用できます。 使用して高速モードでプロファイリングを行う、ときに、 **INC**命令データ カウンター数を増やします。 **INC**命令は高速ですが、スレッド セーフではありません。 使用してプロファイリングをセーフ モードでは、ときに、 **LOCK INC**命令データ カウンター数を増やします。 **LOCK INC**命令と同じ機能を持つ、 **INC**命令があり、スレッド セーフですよりも低速、 **INC**命令します。  
  
 既定では、PGO プロファイリングは高速モードで動作します。 `PogoSafeMode` は、セーフ モードを使用する場合にのみ必要です。  
  
 PGO プロファイリングをセーフ モードでを実行する、環境変数を使用する必要がありますか、`PogoSafeMode`かリンカー スイッチ**- PogoSafeMode**、システムによって異なります。 x64 コンピューターでプロファイリングを実行する場合は、リンカー スイッチを使用する必要があります。 x86 コンピューターでプロファイリングを実行する場合は、最適化処理を開始する前に、環境変数を任意の値に定義する必要があります。  
  
## <a name="example"></a>例  
  
```  
set PogoSafeMode=1  
```  
  
## <a name="see-also"></a>参照  
 [プロファイル ガイド付き最適化のための環境変数](../../build/reference/environment-variables-for-profile-guided-optimizations.md)   
 [ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)