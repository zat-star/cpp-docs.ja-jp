---
title: "&lt;allocators&gt; マクロ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9cb5ee07-1ff9-4594-ae32-3c8c6efb511a
caps.latest.revision: 12
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: da17f9af1f14df13eb3871ef9ccf785356e02de4
ms.openlocfilehash: abc1dd29ba68540a6669f7aff1bbd3dffdab616a
ms.lasthandoff: 02/24/2017

---
# <a name="ltallocatorsgt-macros"></a>&lt;allocators&gt; マクロ
||||  
|-|-|-|  
|[ALLOCATOR_DECL](#allocator_decl)|[CACHE_CHUNKLIST](#cache_chunklist)|[CACHE_FREELIST](#cache_freelist)|  
|[CACHE_SUBALLOC](#cache_suballoc)|[SYNC_DEFAULT](#sync_default)|  
  
##  <a name="a-nameallocatordecla--allocatordecl"></a><a name="allocator_decl"></a>  ALLOCATOR_DECL  
 アロケーター テンプレート クラスを生成します。  
  
```
#define ALLOCATOR_DECL(cache, sync, name) <alloc_template>
```  
  
### <a name="remarks"></a>コメント  
 マクロはテンプレート定義 `template <class Type> class name {.....}` と特殊化 `template <> class name<void> {.....}` を生成します。これらは両方で同期フィルター `sync` と型 `cache` のキャッシュを使用するアロケーター テンプレート クラスを定義します。  
  
 再バインドをコンパイルできるコンパイラの場合、作成されるテンプレート定義は次のようになります。  
```  
struct rebind
   {    /* convert a name<Type> to a name<Other> */
   typedef name<Other> other;
   };  
 ```  
 再バインドをコンパイルできないコンパイラの場合、作成されるテンプレート定義は次のようになります。  
  
```
template <class Type<class name
    : public stdext::allocators::allocator_base<Type,
    sync<stdext::allocators::rts_alloc<cache>>>
{
public:
    name() {}
    template <class Other>
    name(const name<Other>&) {}
    template <class Other>
    name& operator= (const name<Other>&)
    {
        return *this;
    }
};
```  
  
##  <a name="a-namecachechunklista--cachechunklist"></a><a name="cache_chunklist"></a>  CACHE_CHUNKLIST  
 `stdext::allocators::cache_chunklist<sizeof(Type)>` を生成します。  
  
```
#define CACHE_CHUNKLIST <cache_class>
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namecachefreelista--cachefreelist"></a><a name="cache_freelist"></a>  CACHE_FREELIST  
 `stdext::allocators::cache_freelist<sizeof(Type), max>` を生成します。  
  
```
#define CACHE_FREELIST(max) <cache_class>
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namecachesuballoca--cachesuballoc"></a><a name="cache_suballoc"></a>  CACHE_SUBALLOC  
 `stdext::allocators::cache_suballoc<sizeof(Type)>` を生成します。  
  
```
#define CACHE_SUBALLOC <cache_class>
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesyncdefaulta--syncdefault"></a><a name="sync_default"></a>  SYNC_DEFAULT  
 同期フィルターを生成します。  
  
```
#define SYNC_DEFAULT <sync_template>
```  
  
### <a name="remarks"></a>コメント  
 コンパイラがシングル スレッド アプリケーションとマルチ スレッド アプリケーションの両方のコンパイルをサポートしている場合、マクロはシングル スレッド アプリケーションには `stdext::allocators::sync_none` を生成し、それ以外の場合は `stdext::allocators::sync_shared` を生成します。  
  
## <a name="see-also"></a>関連項目  
 [\<allocators>](../standard-library/allocators-header.md)





