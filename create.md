def create
    @article = Article.find(params[:article])
    @article.save
end
