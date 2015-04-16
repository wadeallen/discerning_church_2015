require "jekyll"

desc "Generate blog files"
task :generate do
  Jekyll::Site.new(Jekyll.configuration({
  })).process
end

desc "Publish to Git Hub"
task :publish do
    system "git add ."
    system "git add -u"
    message = "Site updated at #{Time.now.utc}"
    system "git commit -m #{message.inspect}"
    system "git push"
    system "git subtree push --prefix _site origin gh-pages"
  end

task :default => [:generate, :publish]