# 内核文档选译

内核文档是采用sphinx撰写，这种文档撰写方法值得借鉴，可以作为自己技术工作文档撰写指南。

我想选择一些自己感兴趣的项目做一些选译，基于Kernel Document的翻译来学习。

> Linux Kernel Documentation是包含在 [Linux](https://github.com/torvalds/linux) 内核源代码的 Documentation 目录下，下载源代码之后就可以阅读。

> `License`: 文档翻译自Linux Kernel Document，应该是和内核相同的GPL协议

# 

* 从Linux Kernel Documentation目录复制出需要选译的文档子目录

```bash
src_doc_dir=/usr/src/kernels/linux/Documentation
dst_doc_dir=/home/huatai/github/kernel-doc

cp $src_doc_dir/index.rst $dst_doc_dir/
cp $src_doc_dir/conf.py $dst_doc_dir/
cp -R $src_doc_dir/sphinx $dst_doc_dir/
cp -R $src_doc_dir/admin-guide $dst_doc_dir/
cp -R $src_doc_dir/kernel-hacking $dst_doc_dir/
cp -R $src_doc_dir/doc-guide $dst_doc_dir/
cp -R $src_doc_dir/vm $dst_doc_dir/
cp -R $src_doc_dir/trace $dst_doc_dir/
```

* 将文档版本明确写入config.py文件（在Documentation是根据Makefile中配置获得）:

```
echo "version = release = 'v4.20.0'" >> conf.py
```

> 以上步骤已经执行过一次，无需再次执行

* 使用如下命令来构建文档：

```
sphinx-build -b html . output
```

输出的文档位于 `output` 子目录，可以很方便做文档翻译。
