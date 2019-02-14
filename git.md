> ##  上线操作
>
> > 基本操作
> >
> > *  新建分支  
> >
> >   ``` 
> >   git checkout -b feature/pepe-ceshi
> >   git checkout -b hotfix-v1.1.1/pepe-hotfix
> >   ```
> >
> > * 修改后提交
> >
> >   ``` js
> >   git add .
> >   git commit -a
> >   git push
> >   git tag --sort version:refname // 查看最新的tag
> >   git tag -a v2.11.0
> >   git push origin v2.11.0
> >   ```
> >
> > * 回滚分支
> >
> >   ```
> >   git checkout <tag>
> >   ```
> >
> >   
>
> 