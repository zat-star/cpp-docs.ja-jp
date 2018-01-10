---
title: "pgomgr |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8cbb9a4f8b92a1cd495e1312c1aa8a8f77cefcd3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="pgomgr"></a>pgomgr
.Pgd ファイルを 1 つまたは複数の .pgc ファイルからプロファイル データを追加します。  
  
## <a name="syntax"></a>構文  
  
```  
pgomgr [options] pgcfiles pgdfile  
```  
  
#### <a name="parameters"></a>パラメーター  
 `options`  
 Pgomgr には、次のオプションを指定できます。  
  
 **/help —**pgomgr の使用可能なオプションが表示されます (の略/しますか?) です。  
  
 **/clear —**.pgd ファイルすべてのプロファイル情報をクリアします。 .Pgc を指定することはできませんファイル**/clear**を指定します。  
  
 **/detail**— フロー グラフのカバレッジ情報を含む、詳細な統計情報を表示します。  
  
 **/summary**— 表示関数ごとの統計情報。  
  
 **一意/**— と共に使用すると**/summary**原因、装飾関数名を表示します。  既定値、一意では/非装飾関数名を表示するのには使用されません。  
  
 **/merge**[**:***n*]**—**.pgc ファイルまたは .pgd ファイルを追加するファイルのデータ。  省略可能なパラメーター、  *n* 、hat のデータを追加するかを指定する *n* 回です。  たとえば、シナリオは、一般的に 6 回を実行してありますが場合、テストの実行で 1 回行うことして 6 回 .pgd ファイルに追加**した後**です。  
  
 `pgcfiles`  
 1 つまたは複数の .pgc ファイルの .pgd ファイルにマージするプロファイル データを含むです。 単一 .pgc ファイルまたは複数の .pgc ファイルを指定することができます。 .Pgc ファイルを指定しない場合、pgomgr は .pgd ファイルと同じファイル名を持つ、すべての .pgc ファイルをマージします。  
  
 `pgdfile`  
 .Pgc ファイルまたはファイルからデータをマージ先 .pgd ファイルです。  
  
## <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このツールは、[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] コマンド プロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。  
  
## <a name="example"></a>例  
 次の例では、プロファイル データの .pgd ファイルが消去されました。  
  
```  
pgomgr /clear myapp.pgd  
```  
  
 次の例では、myapp1.pgc でプロファイル データは、3 回 .pgd ファイルに追加されました。  
  
```  
pgomgr /merge:3 myapp1.pgc myapp.pgd  
```  
  
 次の例では、すべての myapp!#.pgc ファイルからのプロファイル データが myapp.pgd ファイルに追加されます。  
  
```  
pgomgr -merge myapp1.pgd  
```  
  
## <a name="see-also"></a>参照  
 [ガイド付き最適化の手動プロファイル用ツール](../../build/reference/tools-for-manual-profile-guided-optimization.md)