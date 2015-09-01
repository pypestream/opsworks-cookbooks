desc "install all cookbooks and synchronize them to GitHub"
task :default do
  puts "## Installing cookbooks"
  system "librarian-chef install"
  puts "## Pushing cookbooks to GitHub"
  cd "cookbooks" do
    system %Q(echo "gitdir: ../.git/modules/cookbooks" > .git)
    system "git add ."
    system "git add -u"
    message = "Cookbooks generated via librarian-chef at #{Time.now.utc}"
    system "git commit -m \"#{message}\""
    system "git pull"
    system "git push origin cookbooks"
  end
  puts "## Done!"
end
